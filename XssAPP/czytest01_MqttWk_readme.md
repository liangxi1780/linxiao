# MqttWk by netty

基于 nutzboot + netty + redis + kafka 实现的MQTT服务broker

本项目代码主要来源于 netty/iot-mqtt-server 等众多项目，开源免费，欢迎交流学习

#### QQ交流群
* MqttWk 群号: 225991747
* NutzWk ②群: 24457628 
`作者开发的Java微服务分布式开源框架`

# 参考项目

* [https://github.com/netty/netty](https://github.com/netty/netty)
* [https://gitee.com/recallcode/iot-mqtt-server](https://gitee.com/recallcode/iot-mqtt-server)

# 使用说明

#### 软件架构说明

1. 使用netty实现通信及协议解析
2. 使用nutzboot提供依赖注入及属性配置
3. 使用redis实现消息缓存,集群
4. 使用kafka实现消息代理

#### 项目结构
```
MqttWk
  ├── mqtt-auth -- MQTT服务连接时用户名和密码认证
  ├── mqtt-broker -- MQTT服务器功能的核心实现
  ├── mqtt-common -- 公共类及其他模块使用的服务接口及对象
  ├── mqtt-store -- MQTT服务器会话信息(redis缓存及kafka加载)
  ├── mqtt-zoo -- 教程文档或文件
    ├── mqtt-test-kafka -- kafka消费者接收消息
    ├── mqtt-test-websocket -- websocket通信测试示例
```

#### 功能说明
1. 参考MQTT3.1.1规范实现
2. 完整的QoS服务质量等级实现
3. 遗嘱消息, 保留消息及消息分发重试
4. 心跳机制
5. MQTT连接认证(可选择是否开启)
5. SSL方式连接(可选择是否开启)
6. 主题过滤(支持单主题订阅如 `test_topic`  `/mqtt/test` --不能以/结尾, 通配符订阅 `#` `/mqtt/#` --以#结尾)
7. Websocket支持(可选择是否开启)
8. 集群功能(可选择是否开启)
9. Kafka消息转发功能(可选择是否开启)

#### 快速开始
- JDK1.8
- 项目根目录执行  `mvn install` 
- mqtt-broker 下执行 `mvn clean package nutzboot:shade` 进行打包
- `java -jar mqtt-broker-xxx.jar -Dnutz.profiles.active=prod` [此时加载application-prod.properties配置文件]
- 打开mqtt-spy客户端, 填写相应配置[下载](https://github.com/eclipse/paho.mqtt-spy/wiki/Downloads)
- 连接端口:8885, websocket 端口: 9995 websocket
- 连接使用的用户名: demo
- 连接使用的密码: 8F3B8DE2FDC8BD3D792BE77EAC412010971765E5BDD6C499ADCEE840CE441BDEF17E30684BD95CA708F55022222CC6161D0D23C2DFCB12F8AC998F59E7213393
- 连接使用的证书在 `mqtt-zoo`\keystore\server.cer

#### 集群使用
- 多机环境集群:
  - `mqttwk.broker.cluster-on=true`
  - `mqttwk.broker.kafka.bootstrap.servers=192.168.1.101:9092,192.168.1.102:9093`
  - `redis.mode=cluster` 
  - `redis.nodes=192.168.1.103:16379,192.168.1.104:26379`
- 单机环境集群: 
  - `mqttwk.broker.cluster-on=true`
  - `mqttwk.broker.kafka.bootstrap.servers=127.0.0.1:9092,127.0.0.1:9093`
  - `redis.mode=normal`
  - `redis.host=127.0.0.1`

#### 自定义 - 连接认证
- 默认只是简单使用对用户名进行RSA密钥对加密生成密码, 连接认证时对密码进行解密和相应用户名进行匹配认证
- 使用中如果需要实现连接数据库或其他方式进行连接认证, 只需要重写`mqtt-auth`模块下的相应方法即可

#### 自定义 - 服务端证书
- 服务端证书存储在`mqtt-broker`的`resources/keystore/server.pfx`
- 用户可以制作自己的证书, 但存储位置和文件名必须使用上述描述的位置及文件名

#### 生产环境部署
- 多机环境集群
- 负载均衡: 富人用 L4 Switch,穷人用 Linux HAProxy

#### 示例截图
![示例截图](mqtt-zoo/test.png)

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)