# Harbor

[![Build Status](https://travis-ci.org/goharbor/harbor.svg?branch=master)](https://travis-ci.org/goharbor/harbor)
[![Coverage Status](https://coveralls.io/repos/github/goharbor/harbor/badge.svg?branch=master)](https://coveralls.io/github/goharbor/harbor?branch=master)
[![Go Report Card](https://goreportcard.com/badge/github.com/goharbor/harbor)](https://goreportcard.com/report/github.com/goharbor/harbor)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/2095/badge)](https://bestpractices.coreinfrastructure.org/projects/2095)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/c8d726c9cfd047ffaf681449d673f246)](https://www.codacy.com/app/goharbor/harbor?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=goharbor/harbor&amp;utm_campaign=Badge_Grade)
[![Nightly Status](https://us-central1-eminent-nation-87317.cloudfunctions.net/harbor-nightly-result)](https://www.googleapis.com/storage/v1/b/harbor-nightly/o)

 

|![notification](docs/img/bell-outline-badged.svg)Community Meeting|
|------------------|
|The Harbor Project holds bi-weekly community calls, to join them and watch previous meeting notes and recordings, please see [meeting schedule](https://github.com/goharbor/community/blob/master/MEETING_SCHEDULE.md).|
 

**Note**: The `master` branch may be in an *unstable or even broken state* during development.
Please use [releases](https://github.com/vmware/harbor/releases) instead of the `master` branch in order to get stable binaries.

 

Harbor is an an open source trusted cloud native registry project that stores, signs, and scans content. Harbor extends the open source Docker Distribution by adding the functionalities usually required by users such as security, identity and management. Having a registry closer to the build and run environment can improve the image transfer efficiency. Harbor supports replication of images between registries, and also offers advanced security features such as user management, access control and activity auditing.

Harbor is hosted by the [Cloud Native Computing Foundation](https://cncf.io) (CNCF). If you are an organization that wants to help shape the evolution of cloud native technologies, consider joining the CNCF. For details about who's involved and how Harbor plays a role, read the CNCF
[announcement](https://www.cncf.io/blog/2018/07/31/cncf-to-host-harbor-in-the-sandbox/).

## Features

* **Cloud native registry**: With support for both container images and [Helm](https://helm.sh) charts, Harbor serves as registry for cloud native environments like container runtimes and orchestration platforms.
* **Role based access control**: Users and repositories are organized via 'projects' and a user can have different permission for images under a project.
* **Policy based image replication**: Images can be replicated (synchronized) between multiple registry instances based on policies with multiple filters (repository, tag and label). Harbor will auto-retry to replicate if it encounters any errors. Great for load balancing, high availability, multi-datacenter, hybrid and multi-cloud scenarios.
* **Vulnerability Scanning**: Harbor scans images regularly and warns users of vulnerabilities.
* **LDAP/AD support**: Harbor integrates with existing enterprise LDAP/AD for user authentication and management, and supports importing LDAP groups into Harbor and assigning proper project roles to them.  
* **Image deletion & garbage collection**: Images can be deleted and their space can be recycled.
* **Notary**: Image authenticity can be ensured.
* **Graphical user portal**: User can easily browse, search repositories and manage projects.
* **Auditing**: All the operations to the repositories are tracked.
* **RESTful API**: RESTful APIs for most administrative operations, easy to integrate with external systems.
* **Easy deployment**: Provide both an online and offline installer.

## Install & Run

**System requirements:**

**On a Linux host:** docker 17.03.0-ce+ and docker-compose 1.10.0+ .

Download binaries of **[Harbor release ](https://github.com/vmware/harbor/releases)** and follow **[Installation & Configuration Guide](docs/installation_guide.md)** to install Harbor.

If you want to deploy Harbor on Kubernetes, please use the **[Harbor chart](https://github.com/goharbor/harbor-helm)**.

Refer to **[User Guide](docs/user_guide.md)** for more details on how to use Harbor.

## Community

* **Twitter:** [@project_harbor](https://twitter.com/project_harbor)  
* **User Group:** Join Harbor user email group: [harbor-users@lists.cncf.io](https://lists.cncf.io/g/harbor-users) to get update of Harbor's news, features, releases, or to provide suggestion and feedback.  
* **Developer Group:** Join Harbor developer group: [harbor-dev@lists.cncf.io](https://lists.cncf.io/g/harbor-dev) for discussion on Harbor development and contribution.
* **Slack:** Join Harbor's community for discussion and ask questions: [Cloud Native Computing Foundation](https://slack.cncf.io/), channel: [#harbor](https://cloud-native.slack.com/messages/harbor/) and [#harbor-dev](https://cloud-native.slack.com/messages/harbor-dev/)

## Additional Tools

Tools layered on top of Harbor and contributed by community.

* **[Harbor.Tagd](https://github.com/HylandSoftware/Harbor.Tagd)**
  - Automates the process of cleaning up old tags from your Harbor container registries.
  - Lead by [@nlowe](https://github.com/nlowe) from HylandSoftware.

## Demos

* **[Live Demo](https://demo.goharbor.io)** - A demo environment with the latest Harbor stable build installed. For additional information please refer to [this page](docs/demo_server.md).
* **[Video Demos](https://github.com/goharbor/harbor/wiki/Video-demos-for-Harbor)** - Demos for Harbor features and continuously updated.

## Partners and Users

For a list of users, please refer to [ADOPTERS.md](ADOPTERS.md).

## License

Harbor is available under the [Apache 2 license](LICENSE).

This project uses open source components which have additional licensing terms.  The official docker images and licensing terms for these open source components can be found at the following locations:

* Photon OS 1.0: [docker image](https://hub.docker.com/_/photon/), [license](https://github.com/vmware/photon/blob/master/COPYING)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)