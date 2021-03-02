

![Pinpoint](web/src/main/webapp/images/logo.png)

[![Build Status](https://travis-ci.org/naver/pinpoint.svg?branch=master)](https://travis-ci.org/naver/pinpoint)
[![codecov](https://codecov.io/gh/naver/pinpoint/branch/master/graph/badge.svg)](https://codecov.io/gh/naver/pinpoint)

**Visit [our official web site](http://naver.github.io/pinpoint/) for more information and [Latest updates on Pinpoint](https://naver.github.io/pinpoint/news.html)**.

## Live Demo

Take a quick look at Pinpoint with our [demo](http://125.209.240.10:10123).

## Latest News (2018/08/30)

Pinpoint has started to support application written in PHP. [Check-out our php-agent repository](https://github.com/naver/pinpoint-c-agent).

## Latest Release (2019/06/11)

We're happy to announce the release of Pinpoint v1.8.4.
Please check the release note at (https://github.com/naver/pinpoint/releases/tag/1.8.4).

The current stable version is [v1.8.4](https://github.com/naver/pinpoint/releases/tag/1.8.4).

## About Pinpoint

**Pinpoint** is an APM (Application Performance Management) tool for large-scale distributed systems written in Java / [PHP](https://github.com/naver/pinpoint-c-agent).
Inspired by [Dapper](http://research.google.com/pubs/pub36356.html "Google Dapper"),
Pinpoint provides a solution to help analyze the overall structure of the system and how components within them are interconnected by tracing transactions across distributed applications.

You should definitely check **Pinpoint** out If you want to

* understand your *[application topology](https://naver.github.io/pinpoint/overview.html#overview)* at a glance
* monitor your application in *Real-Time*
* gain *code-level visibility* to every transaction
* install APM Agents *without changing a single line of code*
* have minimal impact on the performance (approximately 3% increase in resource usage)

## Getting Started
 * [Quick-start guide](https://naver.github.io/pinpoint/1.7.3/quickstart.html) for simple test run of Pinpoint
 * [Installation guide](https://naver.github.io/pinpoint/1.7.3/installation.html) for further instructions.
 
## Overview
Services nowadays often consist of many different components, communicating amongst themselves as well as making API calls to external services. How each and every transaction gets executed is often left as a blackbox. Pinpoint traces transaction flows between these components and provides a clear view to identify problem areas and potential bottlenecks. 
For a more intimate guide, please check out our *[Introduction to Pinpoint](http://naver.github.io/pinpoint/#want-a-quick-tour)* video clip.

* **ServerMap** - Understand the topology of any distributed systems by visualizing how their components are interconnected. Clicking on a node reveals details about the component, such as its current status, and transaction count.
* **Realtime Active Thread Chart** - Monitor active threads inside applications in real-time.
* **Request/Response Scatter Chart** - Visualize request count and response patterns over time to identify potential problems. Transactions can be selected for additional detail by **dragging over the chart**.

  ![Server Map](doc/images/ss_server-map.png)

* **CallStack** - Gain code-level visibility to every transaction in a distributed environment, identifying bottlenecks and points of failure in a single view.

  ![Call Stack](doc/images/ss_call-stack.png)

* **Inspector** - View additional details on the application such as CPU usage, Memory/Garbage Collection, TPS, and JVM arguments.

  ![Inspector](doc/images/ss_inspector.png)

## Supported Modules
* JDK 6+
* [Tomcat 6/7/8/9](https://github.com/naver/pinpoint/tree/master/plugins/tomcat), [Jetty 8/9](https://github.com/naver/pinpoint/tree/master/plugins/jetty), [JBoss EAP 6/7](https://github.com/naver/pinpoint/tree/master/plugins/jboss), [Resin 4](https://github.com/naver/pinpoint/tree/master/plugins/resin), [Websphere 6/7/8](https://github.com/naver/pinpoint/tree/master/plugins/websphere), [Vertx 3.3/3.4/3.5](https://github.com/naver/pinpoint/tree/master/plugins/vertx), [Weblogic 10/11g/12c](https://github.com/naver/pinpoint/tree/master/plugins/weblogic), [Undertow](https://github.com/naver/pinpoint/tree/master/plugins/undertow)
* Spring, Spring Boot (Embedded Tomcat, Jetty, Undertow), Spring asynchronous communication
* Apache HTTP Client 3.x/4.x, JDK HttpConnector, GoogleHttpClient, OkHttpClient, NingAsyncHttpClient, Akka-http, Apache CXF
* Thrift Client, Thrift Service, DUBBO PROVIDER, DUBBO CONSUMER, GRPC
* ActiveMQ, RabbitMQ, Kafka
* MySQL, Oracle, MSSQL(jtds), CUBRID, POSTGRESQL, MARIA
* Arcus, Memcached, Redis([Jedis](https://github.com/naver/pinpoint/blob/master/plugins/redis), [Lettuce](https://github.com/naver/pinpoint/tree/master/plugins/redis-lettuce)), CASSANDRA, MongoDB, Hbase
* iBATIS, MyBatis
* DBCP, DBCP2, HIKARICP, DRUID
* gson, Jackson, Json Lib, Fastjson
* log4j, Logback

## Compatibility

Java version required to run Pinpoint:

Pinpoint Version | Agent | Collector | Web
---------------- | ----- | --------- | ---
1.0.x | 6-8 | 6-8 | 6-8
1.1.x | 6-8 | 7-8 | 7-8
1.5.x | 6-8 | 7-8 | 7-8
1.6.x | 6-8 | 7-8 | 7-8
1.7.x | 6-8 | 8 | 8
1.8.0 | 6-10 | 8 | 8 
1.8.1+ | 6-11 | 8 | 8 

HBase compatibility table:

Pinpoint Version | HBase 0.94.x | HBase 0.98.x | HBase 1.0.x | HBase 1.2.x | HBase 2.0.x
---------------- | ------------ | ------------ | ----------- | ----------- | -----------
1.0.x | yes | no | no | no | no
1.1.x | no | not tested | yes | not tested | no
1.5.x | no | not tested | yes | not tested | no
1.6.x | no | not tested | not tested | yes | no
1.7.x | no | not tested | not tested | yes | no
1.8.x | no | not tested | not tested | yes | no

Agent - Collector compatibility table:

Agent Version | Collector 1.0.x | Collector 1.1.x | Collector 1.5.x | Collector 1.6.x | Collector 1.7.x | Collector 1.8.x
------------- | --------------- | --------------- | --------------- | --------------- | --------------- | ---------------
1.0.x | yes | yes | yes | yes | yes | yes
1.1.x | not tested | yes | yes | yes | yes | yes
1.5.x | no | no | yes | yes | yes | yes
1.6.x | no | no | not tested | yes | yes | yes
1.7.x | no | no | no | no | yes | yes
1.8.x | no | no | no | no | no | yes

Flink compatibility table:

Pinpoint Version | flink 1.3.X | flink 1.4.X | flink 1.5.X | flink 1.6.X | flink 1.7.X
---------------- | ----------- | ----------- | ----------- | ----------- | ----------- 
1.7.x | yes | yes | no | no | no |
1.8.x | yes | yes | no | no | no |
1.9.x | yes | yes | yes | yes | yes |

## User Group
For Q/A and discussion [here](https://groups.google.com/forum/#!forum/pinpoint_user).

## License
Pinpoint is licensed under the Apache License, Version 2.0.
See [LICENSE](LICENSE) for full license text.

```
Copyright 2018 NAVER Corp.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)