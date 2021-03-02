Apache SkyWalking | [中文](README_ZH.md)
==========

 

**SkyWalking**: APM (application performance monitor) tool for distributed systems, especially designed for 
microservices, cloud native and container-based (Docker, K8s, Mesos) architectures.
Underlying technology is a distributed tracing system.

[![GitHub stars](https://img.shields.io/github/stars/apache/incubator-skywalking.svg?style=for-the-badge&label=Stars&logo=github)](https://github.com/apache/incubator-skywalking)
[![Twitter Follow](https://img.shields.io/twitter/follow/asfskywalking.svg?style=for-the-badge&label=Follow&logo=twitter)](https://twitter.com/AsfSkyWalking)

[![Build Status](https://travis-ci.org/apache/incubator-skywalking.svg?branch=master)](https://travis-ci.org/apache/incubator-skywalking)
[![Join the chat at https://gitter.im/sky-walking/Lobby](https://badges.gitter.im/openskywalking/Lobby.svg)](https://gitter.im/openskywalking/Lobby)
[![OpenTracing-1.x Badge](https://img.shields.io/badge/OpenTracing--1.x-enabled-blue.svg)](http://opentracing.io)

* Provide Java agent, **no need to CHANGE any application source code**.
  * High performance agent. Only increase extra **10%** cpu cost in 5000+ tps application, even **when collect all traces**.
  * [Supported middlewares, frameworks and libraries](docs/Supported-list.md).
* Manual instrumentation
  * As an [OpenTracing supported tracer](http://opentracing.io/documentation/pages/supported-tracers)
  * Use **@Trace** annotation for any methods you want to trace.
  * Integrate traceId into logs for log4j, log4j2 and logback.
* Pure Java server implementation, provide RESTful and gRPC services. Compatibility with other language agents/SDKs. 
* The UI released on [skywalking-ui](https://github.com/apache/incubator-skywalking-ui)

# Document
[![EN doc](https://img.shields.io/badge/document-English-blue.svg)](docs/README.md) [![cn doc](https://img.shields.io/badge/文档-中文版-blue.svg)](docs/README_ZH.md)

# 5.x Architecture
 

# Code of conduct
This project adheres to the Contributor Covenant [code of conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to wusheng@apache.org.

# Screenshots
- Discovery topological graph of application clusters automatically.
 

- Trace query.
 

- Span detail.
 

- Instance Overview.
 

- JVM Detail.
 

- Services Dependency Tree.
 

# Test reports
- Automatic integration test reports
  - [Java Agent test report](https://github.com/SkywalkingTest/agent-integration-test-report)
- Performance test reports
  - [Java Agent test report](https://skywalkingtest.github.io/Agent-Benchmarks/)

# Contact Us
* Submit an issue
* [Gitter](https://gitter.im/openskywalking/Lobby)
* QQ Group: 392443393

# License
[Apache 2.0 License.](/LICENSE)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)