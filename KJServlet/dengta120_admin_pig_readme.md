 
  
   
   
   
   
   

# Pig Microservice Architecture  
---
**基于Spring Cloud、OAuth2.0、Vue的前后端分离的权限管理系统**      
   
您可以点击这里 在线体验  ,更多开发资料请参考 官网 。如需生产技术支持，请联系 我们 免费支持   
 
最新版本请关注 升级版 , 交流群 23754102  
 
     
    

 ### 模块说明
``` lua
pig
├── pig-ui -- element-vue-admin实现[8000]
├── pig-auth -- 授权服务提供[3000]
├── pig-common -- 系统公共模块 
├── pig-config -- 配置中心[4001]
├── pig-eureka -- 服务注册与发现[1025]
├── pig-gateway -- ZUUL网关[9999]
├── pig-modules -- 微服务模块
├    ├── pig-daemon-service -- 分布式调度中心[4060]
├    ├── pig-mc-service -- 消息中心[4050]
├    ├── pig-sso-client-demo -- 单点登录客户端示例[4040]
├    └── pig-upms-service -- 权限管理提供[4000]
└── pig-visual  -- 图形化模块 
     ├── pig-monitor -- 服务状态监控、turbine [5001]
     ├── pig-zipkin-elk -- zipkin、ELK监控[5002、5601]
     └── pig-cache-cloud -- 缓存管理、统一监控[5005]
```
### 功能列表
- 完善登录：账号密码模式、短信验证码模式、社交账号模式均整合Spring security oAuth
- 单点登录：基于Srping security oAuth 提供单点登录接口，方便其他系统对接
- 用户管理：用户是系统操作者，该功能主要完成系统用户配置。
- 机构管理：配置系统组织机构，树结构展现，可随意调整上下级。
- 菜单管理：配置系统菜单，操作权限，按钮权限标识等。
- 角色管理：角色菜单权限分配、设置角色按机构进行数据范围权限划分。
- 动态路由：基于zuul实现动态路由，后端可配置化。
- 灰度发布：自定义ribbon路由规则匹配多版本请求。
- 终端管理：动态配置oauth终端，后端可配置化。
- 字典管理：对系统中经常使用的一些较为固定的数据进行维护，如：是否等。
- 操作日志：系统正常操作日志记录和查询；系统异常信息日志记录和查询。
- 服务限流：多种维度的流量控制（服务、IP、用户等）
- 消息总线：配置动态实时刷新
- 分库分表：shardingdbc分库分表策略
- 数据权限: 使用mybatis对原查询做增强，业务代码不用控制，即可实现。
- 文件系统: 支持FastDFS、七牛云，扩展API几行代码实现上传下载
- 消息中心：短信、邮件模板发送，几行代码实现发送
- 聚合文档：基于zuul实现 swagger各个模块的实现
- 代码生成：前后端代码的生成，支持Vue
- 缓存管理：基于Cache Cloud 保证Redis 的高可用
- 服务监控: Spring Boot Admin
- 分布式任务调度： 基于elastic-job的分布式任务，zookeeper做调度中心
- zipkin链路追踪： 数据保存ELK，图形化展示
- pinpoint链路追踪： 数据保存hbase，图形化展示

### 问题反馈
1. 欢迎提交 [ issue](https://gitee.com/log4j/pig/issues/new?issue%5Bassignee_id%5D=0&issue%5Bmilestone_id%5D=0)，请写清楚遇到问题的原因，浏览器和操作系统环境，重现的流程。 如果有开发能力，建议在本地调试出出错的代码。

2. 不接受功能请求的issue，功能请求可能会被直接关闭，请谅解（正确的方式是打赏并附言）。  

### 系统展示
 
     
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
 


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)