# Portainer agent

## Purpose

The Portainer Agent is a workaround for a Docker API limitation when using the Docker API to manage a Docker environment. The user interactions with specific resources (containers, networks, volumes and images) are limited to those available on the node targeted by the Docker API request.

Docker Swarm mode introduces a concept which is the clustering of Docker nodes. It also adds services, tasks, configs and secrets which are cluster-aware resources. Cluster-aware means that you can query for a list of services or inspect a task inside any node on the cluster, as long as you’re executing the Docker API request on a manager node.

Containers, networks, volumes and images are node specific resources, not cluster-aware. When you, for example, want to list all the volumes available on a node inside your cluster, you will need to send a query to that specific node.

The purpose of the agent aims to allows previously node specific resources to be cluster-aware, all while keeping the Docker API request format. As aforementioned, this means that you only need to execute one Docker API request to retrieve all these resources from every node inside the cluster. In all bringing a better Docker user experience when managing Swarm clusters.

## Technical details

The Portainer agent is basically a cluster of Docker API proxies. Deployed inside a Swarm cluster on each node, it allows the
redirection (proxy) of a Docker API request on any specific node as well as the aggregration of the response of multiple nodes.

At startup, the agent will communicate with the Docker node it is deployed on via the Unix socket/Windows named pipe to retrieve information about the node (name, IP address, role in the Swarm cluster). This data will be shared when the agent will register into the agent cluster.

### Agent cluster

This implementation is using *serf* to form a cluster over a network, each agent requires an address where it will advertise its
ability to be part of a cluster and a join address where it will be able to reach other agents.

### Proxy

The agent works as a proxy to the Docker API on which it is deployed as well as a proxy to the other agents inside the cluster.

In order to proxy the request to the other agents inside the cluster, it introduces a header called `X-PortainerAgent-Target` which can have
the name of any node in the cluster as a value. When this header is specified, the Portainer agent receiving the request will extract its value, retrieve the address of the agent located on the node specified using this header value and proxy the request to it.

If no header `X-PortainerAgent-Target` is present, we assume that the agent receiving the request is the target of the request and it will
be proxied to the local Docker API.

Some requests are specifically marked to be executed against a manager node inside the cluster (`/services/**`, `/tasks/**`, `/nodes/**`, etc... e.g. all the Docker API operations that can only be executed on a Swarm manager node). This means that you can execute these requests
against any agent in the cluster and they will be proxied to an agent (and to the associated Docker API) located on a Swarm manager node.

### Proxy & aggregation

By default, the agent will inspect any requests and search for the `X-PortainerAgent-ManagerOperation` header. If it is found (the value of the header does not matter),
then the agent will proxy that request to an agent located on any manager node. If this header is not found, then an operation will be executed based on the endpoint prefix (`/networks` for a cluster operation, `/services` for a manager operation, etc...).

The `X-PortainerAgent-ManagerOperation` header was introduced to work-around the fact that a Portainer instance uses the Docker CLI binary to manage stacks and the binary
**MUST** always target a manager node when executing any command.

Some requests are specifically marked to be executed against the whole cluster:

* `GET /containers/json`
* `GET /images/json`
* `GET /volumes`
* `GET /networks`

The agent handles these requests using the same header mechanism. If no `X-PortainerAgent-Target` is found, it will automatically execute
the request against each node in the cluster in a concurrent way. Behind the scene, it retrieves the IP address of each node, create a copy of the request, decorate each request with the `X-PortainerAgent-Target` header and aggregate the response of each request into a single one (reproducing the Docker API response format).


### Docker API compliance

When communicating with a Portainer agent instead of using the Docker API directly, the only difference is the possibility to add the `X-PortainerAgent-Target` header to each request to be able to execute some actions against a specific node in the cluster.

The fact that the agent final proxy target is always the Docker API means that we keep the Docker original response format. The only difference in the response is that the agent will automatically add the `Portainer-Agent` header to each response using the version of the Portainer agent as value.

### Agent specific API

The agent also exposes the following endpoints:

* `/agents` (*GET*): List all the available agents in the cluster
* `/browse/ls` (*GET*): List the files available under a specific path on the filesystem
* `/browse/get` (*GET*): Retrieve a file available under a specific path on the filesytem
* `/browse/delete` (*DELETE*): Delete an existing file under a specific path on the filesytem
* `/browse/rename` (*PUT*): Rename an existing file under a specific path on the filesytem
* `/browse/put` (*POST*): Upload a file under a specific path on the filesytem
* `/host/info` (*GET*): Get information about the underlying host system
* `/ping` (*GET*): Returns a 204. Public endpoint that do not require any form of authentication

Note: The `/browse/*` endpoints can be used to manage a filesystem. By default, it allows manipulation of files in Docker volumes (available under `/var/run/docker/volumes` when bind-mounted in the agent container) but can also manipulate files anywhere on the filesystem. To enable global
filesystem manipulation support for these endpoints, the `CAP_HOST_MANAGEMENT` environment variable must be set to `1`.

### Agent API version

The agent API version is exposed via the `Portainer-Agent-API-Version` in each response of the agent.

## Security

### Encryption

By default, an agent will automatically generate its own set of TLS certificate and key. It will then use these to start the web
server where the agent API is exposed. By using self-signed certificates, each agent client and proxy will skip the TLS server verification when executing a request against another agent.

### Authentication

Each request to an agent must include a digital signature in the `X-PortainerAgent-Signature` header encoded using the `base64` format (without the padding characters).

![public key cryptography wikipedia](https://user-images.githubusercontent.com/5485061/48817100-ac410b80-eda9-11e8-8d72-ef668e8278df.png)

The following protocol is used between a Portainer instance and an agent:

For each HTTP request made from the Portainer instance to the agent:

1. The Portainer instance generates a signature using its private key. It encodes this signature in base64 and add it to the `X-PortainerAgent-Signature` header of the request
2. The Portainer instance encodes its public key in hexadecimal and adds it the `X-PortainerAgent-PublicKey` header of the request


For each HTTP request received from the agent:

1. The agent will check that the `X-PortainerAgent-PublicKey` and `X-PortainerAgent-Signature` headers are available in the request otherwise it returns a 403
2. The agent will then trigger the signature verification process. If the signature is not valid it returns a 403

#### Signature verification

The signature verification process can follow two different paths based on how the agent was deployed.

##### Default mode

By default, the agent will wait for a valid request from a Portainer instance and automatically associate the first Portainer instance that communicates with it by registering the public key found in the `X-PortainerAgent-PublicKey` header inside memory.

During the association process, the agent will first decode the specified public key from hexadecimal and then parse the public key. Only if these steps are successfull then the key will be associated to the agent.

Once a Portainer instance is registered by the agent, the agent will not try to decode/parse the public key associated to a request anymore and will assume that only signatures associated to this public key are authorized (preventing any other Portainer instance to communicate with this agent).

Finally, the agent uses the associated public key and a default message that is known by both entities to verify the signature available in the `X-PortainerAgent-Signature` header.

##### Secret mode

When the `AGENT_SECRET` environment variable is set in the execution context of the agent (`-e AGENT_SECRET=mysecret` when started as a container for example), the digital signature verification process will be slightly different.

In secret mode, the agent will not register a Portainer public key in memory anymore. Instead, it will **ALWAYS** decode and parse the public key available in the `X-PortainerAgent-PublicKey` and will then trigger the signature verification using key.

The signature verification is slightly altered as well, it now uses the public key sent in the request to verify the signature as well as the secret specified at startup in the `AGENT_SECRET` environment variable.

This mode will allow multiple instances of Portainer to connect to a single agent.

Note: Due to the fact that the agent will now decode and parse the public key associated to each request, this mode might be less performant than the default mode.


## Deployment options

The behavior of the agent can be tuned via a set of mandatory and optional options available as environment variables:

* AGENT_CLUSTER_ADDR (*mandatory*): address (in the IP:PORT format) of an existing agent to join the agent cluster. When deploying the agent as a Docker Swarm service,
we can leverage the internal Docker DNS to automatically join existing agents or form a cluster by using `tasks. : ` as the address.
* AGENT_PORT (*optional*): port on which the agent web server will listen (default to `9001`).
* CAP_HOST_MANAGEMENT (*optional*): enable advanced filesystem management features. Disabled by default, set to `1` to enable it.
* AGENT_SECRET (*optional*): shared secret used in the signature verification process
* LOG_LEVEL (*optional*): defines the log output verbosity (default to `INFO`)

For more information about deployment scenarios, see: https://portainer.readthedocs.io/en/stable/agent.html

## Development

1. Install go >= 1.11.2
2. Install dep: https://golang.github.io/dep/docs/installation.html

If you want to add any extra dependency:

```
dep ensure -add github.com/foo/bar
```

3. Run a local agent container:

```
./dev.sh local
```

4. Run the agent container inside a Swarm cluster (requires https://github.com/deviantony/vagrant-swarm-cluster)

```
./dev.sh swarm
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)