# FristBlood

>### 分布式系统开启篇
>
>> 随着业务发展，需求的不断变更以及用户量的激增。传统的单节点服务面临数据量的瓶颈问题，单个服务里面代码的复杂度都是令人崩溃的问题。为了解决传统开发中遇到的问题，我们尝试着使用微服务的架构进行开发，满足业务快速的发展，避免开发人员重复的、繁琐的代码工作。
>
>#### 何为微服务？
>
>> 我们将传统的单服务系统进行拆分，一个系统由若干的服务协同工作提供服务。每个服务只需要关心自身的业务实现，无需关注其他服务的实现。通过负载均衡可实现多节点热部署，更新版本无需暂停服务，客户端毫无感知。微服务架构方式是松耦合的，可以提供更高的灵活性。
>
>> 同样，我们在使用微服务架构进行开发的同时，也会遇到很多新的挑战。如何保证数据一致性的问题？请求出错时，如何定位问题？服务间通信，消息异步处理问题？这些问题在后面的开发中，我们都会一一解决。
>
>#### Hello World
>
>- 服务介绍
>
>|   服务名    |  服务概述  |
>| :------: | :----: |
>|  eureka  |  注册中心  |
>|  config  |  配置中心  |
>|   zuul   |   路由   |
>|  zipkin  | 请求链路监控 |
>
>- sEureka
>
>> 注册中心，所有的服务都应该注册到注册中心，管理所有的服务状态。
>
>- sConfig
>
>> 配置中心，通过该服务，可一键切换部署环境。服务开发环境用到的参数，都应该通过配置中心配置。
>
>- sZuul
>
>> 路由管理，负责分发各个服务的请求。通过注册中心，实现负载均衡功能。
>
>- sSmsCore
>
>> 短信中心，平台上的发送短信功能应该由短信中心统一管理。其他服务务需调用发送短信问题。
>
>- sUserinfoV1
>
>> 用户资料中心，其他服务如需获取用户的详细资料，可通过用户资料中心提供的接口获取。




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)