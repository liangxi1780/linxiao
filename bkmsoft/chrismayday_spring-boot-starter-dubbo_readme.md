# spring-boot-starter-dubbo

spring-boot-start-dubbo，是spring-boot与dubbo有机结合的桥梁，根据`spring-boot`开箱即用的原则实现，使dubbo的使用变得及其简单快捷，容易上手。让dubbo小白正常使用dubbo，只需一盏茶的功夫。

使用本项目，你肯定会发现，原来`dubbo发布服务如此简单`。

### 本项目特点
###### 1.支持dubbo原生所有的配置项，使用spring-boot方式配置
###### 2.配置项描述清晰，让你在配置参数时，`等同在看dubbo官方中文文档`（需要安装spring-ide插件） ( dubbo中文文档点这里 )
###### 3.提供注解@Inject，用来替换@Reference的依赖注入，让spring+dubbo时依赖注入注解更简单（该注解如果不能从spring上下文注入对象，将使用等同@Reference的依赖注入方式注入对象）

### 简单示例
1.示例项目推荐使用zookeeper作为注册中心，因为线上你肯定会用它。如果你本地没有可用的zookeeper服务，你可以[点击这里下载](http://mirror.bit.edu.cn/apache/zookeeper/zookeeper-3.4.10/zookeeper-3.4.10.tar.gz),下载后解压，进入zookeeper的conf目录，拷贝zoo_sample.cfg它为zoo.cfg，进入zookeeper的bin目录,windows系统下双击zkServer.cmd，linux下执行zkServer.sh命令。

2.下载示例的服务提供者[example-provider](http://central.maven.org/maven2/com/gitee/reger/example-provider/1.0.1/example-provider-1.0.1.jar)，执行命令
```sh
java -jar example-provider-1.0.1.jar --spring.dubbo.address=127.0.0.1  --spring.dubbo.port=2181 
```
3.下载示例的服务调用者[example-consumer](http://central.maven.org/maven2/com/gitee/reger/example-consumer/1.0.1/example-consumer-1.0.1.jar)，执行命令
```sh
java -jar example-consumer-1.0.1.jar --spring.dubbo.address=127.0.0.1  --spring.dubbo.port=2181 
```
4.consumer和provider都有正常调用的日志输出，至此简单示例就运行起来了，也表示你本地的dubbo环境已经可以用了。

5.克隆示例代码，开始`dubbo`之旅。 （ 示例项目点这里 ）
```sh
git clone https://gitee.com/reger/spring-boot-starter-dubbo-example.git
```  
## 快速入门
#### 1.在maven管理的spring-boot项目中引入依赖,（建议使用spring-boot版本1.5以上,1.5以下未测试过）
```xml
     
         com.gitee.reger 
         spring-boot-starter-dubbo 
         ${spring-boot-starter-dubbo.version} 
     
 ```
#### 2.在spring-boot项目的配置文件'application.yml'中增加dubbo的配置项
###### 服务提供者增加
```yml
spring:
  dubbo: 
    application:
      name: demo-provider
    base-package: com.test.dubbo.provider  # dubbo服务发布者所在的包
    registry:
      address: 127.0.0.1                   # zookeeper注册中心的地址
      port: 2181                           # zookeeper注册中心的端口
    protocol:
      name: dubbo
      serialization: hessian2
    provider:
      retries: 0                           # 服务调用重试次数，服务发布者不给重试，让服务调用者自己重试
```
###### 服务调用者增加
```yml
spring:
  dubbo: 
    application:
      name: demo-consumer
    base-package: com.test.dubbo.consumer  # dubbo服务调用者所在的包  
    registry:
      address: 127.0.0.1                   # zookeeper注册中心的地址
      port: 2181                           # zookeeper注册中心的端口
    consumer:
      timeout: 1000 
      check: true                          # 服务启动时检查被调用服务是否可用
      retries: 2                           # 服务调用重试次数 
```
#### 3. 定义服务接口，
在api项目中增加接口
```java
package com.test.dubbo.service;

public interface DemoService {
    Integer add(Integer a,Integer b);
}
```
#### 4. 服务提供者
服务提供者项目中增加业务类
```java
package com.test.dubbo.provider;
import com.test.dubbo.service.DemoService;
import com.alibaba.dubbo.config.annotation.Service;

@Service
public class DemoServiceImpl implements DemoService{

    public Integer add(Integer a,Integer b){
        System.err.printf("方法add被调用 %s+%s", a, b);
        System.err.println();
        if(a==null||b==null){
            return 0;
        }
        return a+b;
    }
}
```
#### 5. 服务调用者
服务调用者项目中增加业务类
```java
package com.test.dubbo.consumer;

import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

import com.alibaba.dubbo.config.annotation.Reference;
import com.reger.dubbo.annotation.Inject;

import com.test.dubbo.service.DemoService;

@Component
public class DemoConsumer implements CommandLineRunner {

    // 使用dubbo原生注入，可以选择使用@Inject兼容注入
    @Reference DemoService service; 

    @Override
    public void run(String... args){  
        int a=1;
        int b =2;
        System.err.printf("%s+%s=%s", a, b, service.add(a,b));
        System.err.println(); 
    }
}
```
#### 6.启动服务提供者，启动服务调用者。
服务提供者spring-boot的main方法的示例
```java
package com.test.dubbo.main;

import java.util.concurrent.TimeUnit;

import org.springframework.boot.CommandLineRunner;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication 
public class SpringDubboConfigApplication implements CommandLineRunner {

    public static void main(String[] args) throws InterruptedException {
        SpringApplication.run(SpringDubboConfigApplication.class, args);
        TimeUnit.MINUTES.sleep(10); //提供者main线程暂停10分钟等待被调用
        System.err.println("服务提供者------>>服务关闭");
    }

    @Override
    public void run(String... args) throws Exception {
        System.err.println("服务提供者------>>启动完毕");
    } 
}
```
服务调用者spring-boot的main方法的类示例
```java
package com.test.dubbo.main;

import org.springframework.boot.CommandLineRunner;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication 
public class SpringDubboConfigApplication implements CommandLineRunner {

    public static void main(String[] args) {
        SpringApplication.run(SpringDubboConfigApplication.class, args);
    }

    @Override
    public void run(String... args) throws Exception {
        System.err.println("服务调用者------>>启动完毕");
    }
}
```
## 可用配置项  

#### 1.应用配置参数(必须配置)
```yml
spring:
  dubbo: 
    application:
      name: demo-provider     # 必填 服务治理 当前应用名称，用于注册中心计算应用间依赖关系，注意：消费者和提供者应用名不要一样，此参数不是匹配条件，你当前项目叫什么名字就填什么，和提供者消费者角色无关，比如：kylin应用调用了morgan应用的服务，则kylin项目配成kylin，morgan项目配成morgan，可能kylin也提供其它服务给别人使用，但kylin项目永远配成kylin，这样注册中心将显示kylin依赖于morgan 1.0.16以上版本
      owner: laolei           # 可选 服务治理 应用负责人，用于服务治理，请填写负责人公司邮箱前缀 2.0.5以上版本
      architecture:           # 可选 服务治理 用于服务分层对应的架构。如，intl、china。不同的架构使用不同的分层。 2.0.7以上版本
      compiler: javassist     # 可选 性能优化 Java字节码编译器，用于动态类的生成，可选：jdk或javassist 2.1.0以上版本
      environment:            # 可选 服务治理 应用环境，如：develop/test/product，不同环境使用不同的缺省值，以及作为只用于开发测试功能的限制条件 2.0.0以上版本
      logger: slf4j           # 可选 性能优化 日志输出方式，可选：slf4j,jcl,log4j,jdk 2.2.0以上版本
      organization:           # 可选 服务治理 组织名称(BU或部门)，用于注册中心区分服务来源，此配置项建议不要使用autoconfig，直接写死在配置中，比如china,intl,itu,crm,asc,dw,aliexpress等 2.0.0以上版本
      version:                # 可选 服务治理 当前应用的版本 2.2.0以上版本
```
#### 2.服务扫描的包（使用注解时必须配置）
```yml
spring:
  dubbo: 
    base-package:             # 提供者service和消费者所在的java包,多个包用逗号分割
```
#### 3.注册中心支持的配置参数 （必须配置）
```yml
spring:
  dubbo:
    registry:               # 应用注册中心配置项
      protocol: zookeeper   # 必填 服务发现 注册中心支持的协议 包括 dubbo,multicast,zookeeper,redis 默认是zookeeper
      address: 127.0.0.1    # 必填 服务发现 注册中心服务器地址，如果地址没有端口缺省为9090，同一集群内的多个地址用逗号分隔，如：ip:port,ip:port，不同集群的注册中心，请配置多个spring.dubbo.registry.标签 1.0.16以上版本
      port: 2181            # 可选 服务发现 注册中心缺省端口，当address没有带端口时使用此端口做为缺省值 2.0.0以上版本
      client: zkclient      # 可选 服务发现 注册中心支持的客户端， zookeeper 支持客户端包括 curator和zkclient,如果不配置，默认使用zkclient 
      session: 60000        # 可选 性能调优 注册中心会话超时时间(毫秒)，用于检测提供者非正常断线后的脏数据，比如用心跳检测的实现，此时间就是心跳间隔，不同注册中心实现不一样。 2.1.0以上版本
      register: true        # 可选 服务治理 是否向此注册中心注册服务，如果设为false，将只订阅，不注册 2.0.5以上版本
      check: false          # 可选 服务治理 服务是否动态注册，如果设为false，注册后将显示后disable状态，需人工启用，并且服务提供者停止时，也不会自动取消册，需人工禁用。 2.0.5以上版本
      dynamic: true         # 可选 服务治理 服务是否动态注册，如果设为false，注册后将显示后disable状态，需人工启用，并且服务提供者停止时，也不会自动取消册，需人工禁用。 2.0.5以上版本
      file: regcache.log    # 可选 服务治理 使用文件缓存注册中心地址列表及服务提供者列表，应用重启时将基于此文件恢复，注意：两个注册中心不能使用同一文件存储 2.0.0以上版本
      username:             # 可选 服务治理 登录注册中心用户名，如果注册中心不需要验证可不填 2.0.0以上版本
      password:             # 可选 服务治理 登录注册中心密码，如果注册中心不需要验证可不填 2.0.0以上版本
      subscribe:            # 可选 服务治理 是否向此注册中心订阅服务，如果设为false，将只注册，不订阅 2.0.5以上版本
      timeout:              # 可选 性能调优 注册中心请求超时时间(毫秒) 2.0.0以上版本
      wait: 0               # 可选 性能调优 停止时等待通知完成时间(毫秒) 2.0.0以上版本
      transport: netty      # 可选 性能调优 网络传输方式，可选mina,netty 2.0.0以上版本
      id:                   # 可选 配置关联 注册中心引用BeanId，可以在 或 中引用此ID 1.0.16以上版本
```
#### 4.服务调用支持的类型（必须配置）
```yml
spring:
  dubbo:
    protocol:               # 默认的应用协议栈
      name: dubbo           # 必填 性能调优 协议名称 2.0.5以上版本
      serialization: hessian2 #可选 性能调优 协议序列化方式，当协议支持多种序列化方式时使用，比如：dubbo协议的dubbo,hessian2,java,compactedjava，以及http协议的json等 2.0.5以上版本
      accepts: 0            # 可选 性能调优 服务提供方最大可接受连接数 2.0.5以上版本
      accesslog: false      # 可选 服务治理 设为true，将向logger中输出访问日志，也可填写访问日志文件路径，直接把访问日志输出到指定文件 2.0.5以上版本
      buffer: 8192          # 可选 性能调优 网络读写缓冲区大小 2.0.5以上版本
      charset: UTF-8        # 可选 性能调优 序列化编码 2.0.5以上版本
      client: netty         # 可选 性能调优 协议的客户端实现类型，比如：dubbo协议的mina,netty等 2.0.5以上版本
      codec: dubbo          # 可选 性能调优 协议编码方式 2.0.5以上版本
      contextpath:          # 可选 服务治理 2.0.6以上版本
      dispatcher: all       # 可选 性能调优 协议的消息派发方式，用于指定线程模型，比如：dubbo协议的all, direct, message, execution, connection等 2.1.0以上版本
      heartbeat: 0          # 可选 性能调优 心跳间隔，对于长连接，当物理层断开时，比如拔网线，TCP的FIN消息来不及发送，对方收不到断开事件，此时需要心跳来帮助检查连接是否已断开 2.0.10以上版本
      host:                 # 可选 服务发现 -服务主机名，多网卡选择或指定VIP及域名时使用，为空则自动查找本机IP，-建议不要配置，让Dubbo自动获取本机IP 2.0.5以上版本 
      id: dubbo             # 可选 配置关联 协议BeanId，可以在 中引用此ID，如果ID不填，缺省和name属性值一样，重复则在name后加序号。 2.0.5以上版本
      iothreads:            # 可选 性能调优 io线程池大小(固定大小) 2.0.5以上版本 
      path:                 # 可选 服务发现 提供者上下文路径，为服务path的前缀 2.0.5以上版本
      payload: 88388608     # 可选 性能调优 请求及响应数据包大小限制，单位：字节 2.0.5以上版本
      port:                 # 可选 服务发现 不输入或者输入0，将自动在53600~53688之间生产一个  服务端口  2.0.5以上版本 ， 
      queues: 0             # 可选 性能调优 线程池队列大小，当线程池满时，排队等待执行的队列大小，建议不要设置，当线程程池时应立即失败，重试其它服务提供机器，而不是排队，除非有特殊需求。 2.0.5以上版本
      register: true        # 可选 服务治理 该协议的服务是否注册到注册中心 2.0.8以上版本
      server:               # 可选 性能调优 协议的服务器端实现类型，比如：dubbo协议的mina,netty等，http协议的jetty,servlet等 2.0.5以上版本
      telnet:               # 可选 服务治理 所支持的telnet命令，多个命令用逗号分隔 2.0.5以上版本
      threadpool: fixed     # 可选 性能调优 线程池类型，可选：fixed/cached 2.0.5以上版本
      threads: 100          # 可选 性能调优 服务线程池大小(固定大小) 2.0.5以上版本
      transporter: netty    # 可选 性能调优 协议的服务端和客户端实现类型，比如：dubbo协议的mina,netty等，可以分拆为server和client配置 2.0.5以上版本
      
#  如果需要配置多个协议可以使用如下方式
#    protocols:
#      - name: dubbo
#        serialization: nativejava
#      - name: dubbo
#        serialization: hessian2
#      - name: dubbo
#        serialization: fastjson
#      - name: dubbo
#        serialization: dubbo
#      - name: rmi
#      - name: http
#      - name: hessian
#      - name: thrift
#      - name: webservice
```
#### 5.提供者默认的配置参数（可选配置）
```yml
spring:
  dubbo: 
    provider:                 # 公用的生产者配置
      retries: -1             # 可选 性能调优 远程服务调用重试次数，不包括第一次调用，不需要重试请设为0 2.0.5以上版本
      accesslog: false        # 可选 服务治理 设为true，将向logger中输出访问日志，也可填写访问日志文件路径，直接把访问日志输出到指定文件 2.0.5以上版本
      delay: 0                # 可选 性能调优 延迟注册服务时间(毫秒)- ，设为-1时，表示延迟到Spring容器初始化完成时暴露服务 2.0.5以上版本
      deprecated: false       # 可选 服务治理 服务是否过时，如果设为true，消费方引用时将打印服务过时警告error日志 2.0.5以上版本
      document:               # 可选 服务治理 服务文档URL 2.0.5以上版本
      dynamic: true           # 可选 服务治理 服务是否动态注册，如果设为false，注册后将显示后disable状态，需人工启用，并且服务提供者停止时，也不会自动取消册，需人工禁用。 2.0.5以上版本
      executes: 0             # 可选 性能调优 服务提供者每服务每方法最大可并行执行请求数 2.0.5以上版本
      group:                  # 可选 服务发现 服务分组，当一个接口有多个实现，可以用分组区分 2.0.5以上版本
      id: dubbo               # 可选 配置关联 协议BeanId，可以在 中引用此ID 1.0.16以上版本
      layer:                  # 可选 服务治理 服务提供者所在的分层。如：biz、dao、intl:web、china:acton。 2.0.7以上版本
      listener:               # 可选 性能调优 服务提供方导出服务监听器名称，多个名称用逗号分隔 2.0.5以上版本
      mock: false             # 可选 服务治理 设为true，表示使用缺省Mock类名，即：接口名 + Mock后缀。 2.0.5以上版本
      owner:                  # 可选 服务治理 服务负责人，用于服务治理，请填写负责人公司邮箱前缀 2.0.5以上版本
      path:                   # 可选 服务发现 提供者上下文路径，为服务path的前缀 2.0.0以上版本 
      protocol: dubbo         # 可选 性能调优 协议名称 1.0.16以上版本
      proxy: javassist        # 可选 性能调优 生成动态代理方式，可选：jdk/javassist 2.0.5以上版本
      registry:               # 可选 配置关联 向指定注册中心注册，在多个注册中心时使用，值为spring.dubbo.registry.的id属性，多个注册中心ID用逗号分隔，如果不想将该服务注册到任何registry，可将值设为N/A 2.0.5以上版本
      stub: false             # 可选 服务治理 设为true，表示使用缺省代理类名，即：接口名 + Local后缀。 2.0.5以上版本
      token: false            # 可选 服务治理 令牌验证，为空表示不开启，如果为true，表示随机生成动态令牌 2.0.5以上版本
      version: 0.0.0          # 可选 服务发现 服务版本，建议使用两位数字版本，如：1.0，通常在接口不兼容时版本号才需要升级 2.0.5以上版本
      weight: 0               # 可选 性能调优 服务权重 2.0.5以上版本
      accepts: 0              # 可选 性能调优 服务提供者最大可接受连接数 2.0.5以上版本
      actives: 0              # 可选 性能调优 每服务消费者每服务每方法最大并发调用数 2.0.5以上版本
      async: false            # 可选 性能调优 是否缺省异步执行，不可靠异步，只是忽略返回值，不阻塞执行线程 2.0.5以上版本
      buffer: 8192            # 可选 性能调优 网络读写缓冲区大小 2.0.5以上版本
      charset: UTF-8          # 可选 性能调优 序列化编码 2.0.5以上版本
      client: netty           # 可选 性能调优 协议的客户端实现类型，比如：dubbo协议的mina,netty等 2.0.0以上版本
      cluster: failover       # 可选 性能调优 集群方式，可选：failover/failfast/failsafe/failback/forking 2.0.5以上版本
      codec: dubbo            # 可选 性能调优 协议编码方式 2.0.0以上版本
      connections: 0          # 可选 性能调优 对每个提供者的最大连接数，rmi、http、hessian等短连接协议表示限制连接数，dubbo等长连接协表示建立的长连接个数 2.0.5以上版本
      default: false          # 可选 配置关联 是否为缺省协议，用于多协议 1.0.16以上版本
      host:                   # 可选 服务发现 服务主机名，多网卡选择或指定VIP及域名时使用，为空则自动查找本机IP，建议不要配置，让Dubbo自动获取本机IP 1.0.16以上版本
      iothreads:              # 可选 性能调优 IO线程池，接收网络读写中断，以及序列化和反序列化，不处理业务，业务线程池参见threads配置，此线程池和CPU相关，不建议配置。 2.0.5以上版本
      loadbalance: random     # 可选 性能调优 负载均衡策略，可选值：random,roundrobin,leastactive，分别表示：随机，轮循，最少活跃调用 2.0.5以上版本
      payload: 88388608       # 可选 性能调优 请求及响应数据包大小限制，单位：字节 2.0.0以上版本
      queues: 0               # 可选 性能调优 线程池队列大小，当线程池满时，排队等待执行的队列大小，建议不要设置，当线程程池时应立即失败，重试其它服务提供机器，而不是排队，除非有特殊需求。 2.0.5以上版本
      serialization: hessian2 # 可选 性能调优 协议序列化方式，当协议支持多种序列化方式时使用，比如：dubbo协议的dubbo,hessian2,java,compactedjava，以及http协议的json,xml等 2.0.5以上版本
      server: netty           # 可选 性能调优 协议的服务器端实现类型，比如：dubbo协议的mina,netty等，http协议的jetty,servlet等 2.0.0以上版本
      telnet:                 # 可选 服务治理 所支持的telnet命令，多个命令用逗号分隔 2.0.5以上版本
      threadpool: fixed       # 可选 性能调优 线程池类型，可选：fixed/cached 2.0.5以上版本
      threads: 100            # 可选 性能调优 线程池类型，可选：fixed/cached 2.0.5以上版本
      timeout: 1000           # 可选 性能调优 远程服务调用超时时间(毫秒) 2.0.5以上版本
      filter:                 # 可选 性能调优 服务提供方远程调用过程拦截器名称，多个名称用逗号分隔 2.0.5以上版本
```
#### 6.调用者默认的配置（可选配置）
```yml
spring:
  dubbo: 
    consumer:                   # 公用的消费者配置
      lazy: true                #
      timeout: 1000             # 可选 性能调优 远程服务调用超时时间(毫秒) 1.0.16以上版本
      check: true               # 可选 服务治理 启动时检查提供者是否存在，true报错，false忽略 1.0.16以上版本
      retries: 2                # 可选 性能调优 远程服务调用重试次数，不包括第一次调用，不需要重试请设为0 1.0.16以上版本
      filter:                   # 可选 性能调优 服务消费方远程调用过程拦截器名称，多个名称用逗号分隔 2.0.5以上版本
      actives: 0                # 可选 性能调优 每服务消费者每服务每方法最大并发调用数 2.0.5以上版本
      async: false              # 可选 性能调优 是否缺省异步执行，不可靠异步，只是忽略返回值，不阻塞执行线程 2.0.0以上版本
      cache:                    # 可选 服务治理 以调用参数为key，缓存返回结果，可选：lru, threadlocal, jcache等 Dubbo2.1.0及其以上版本支持
      cluster: failover         # 可选 性能调优 集群方式，可选：failover/failfast/failsafe/failback/forking 2.0.5以上版本
      connections: 100          # 可选 性能调优 每个服务对每个提供者的最大连接数，rmi、http、hessian等短连接协议支持此配置，dubbo协议长连接不支持此配置 1.0.16以上版本
      generic: false            # 可选 服务治理 是否缺省泛化接口，如果为泛化接口，将返回GenericService 2.0.0以上版本
      init: false               # 可选 性能调优 是否在afterPropertiesSet()时饥饿初始化引用，否则等到有人注入或引用该实例时再初始化。 2.0.10以上版本
      layer:                    # 可选 服务治理 服务调用者所在的分层。如：biz、dao、intl:web、china:acton。 2.0.7以上版本
      listener:                 # 可选 性能调优 服务消费方引用服务监听器名称，多个名称用逗号分隔 2.0.5以上版本
      loadbalance: random       # 可选 性能调优 负载均衡策略，可选值：random,roundrobin,leastactive，分别表示：随机，轮循，最少活跃调用 1.0.16以上版本
      owner:                    # 可选 服务治理 调用服务负责人，用于服务治理，请填写负责人公司邮箱前缀 2.0.5以上版本
      proxy: javassist          # 可选 性能调优 生成动态代理方式，可选：jdk/javassist 2.0.5以上版本
      registry:                 # 可选 配置关联 向指定注册中心注册，在多个注册中心时使用，值为spring.dubbo.registry.的id属性，多个注册中心ID用逗号分隔，如果不想将该服务注册到任何registry，可将值设为N/A 2.0.5以上版本
      retries: 2                # 可选 性能调优 远程服务调用重试次数，不包括第一次调用，不需要重试请设为0 1.0.16以上版本
      validation:               # 可选 服务治理 是否启用JSR303标准注解验证，如果启用，将对方法参数上的注解进行校验 Dubbo2.1.0及其以上版本支持
```
#### 7.监控中心配置参数（可选配置）
```yml
spring:
  dubbo:
    monitor:                # 监控服务
      address: N/A          # 可选 服务治理 直连监控中心服务器地址，address="10.20.130.230:12080" 1.0.16以上版本
      protocol: dubbo       # 可选 服务治理 监控中心协议，如果为protocol="registry"，表示从注册中心发现监控中心地址，否则直连监控中心。 2.0.9以上版本
```
#### 8.模块定义（可选配置）
```yml
spring:
  dubbo:
    module:                 # 应用模块定义
      name:                 # 必填 服务治理 当前模块名称，用于注册中心计算模块间依赖关系 2.2.0以上版本
      organization:         # 可选 服务治理 组织名称(BU或部门)，用于注册中心区分服务来源，此配置项建议不要使用autoconfig，直接写死在配置中，比如china,intl,itu,crm,asc,dw,aliexpress等 2.2.0以上版本
      owner:                # 可选 服务治理 模块负责人，用于服务治理，请填写负责人公司邮箱前缀 2.2.0以上版本
      version:              # 可选 服务治理 当前模块的版本 2.2.0以上版本
```
#### 9.服务提供者发布的服务列表（由于这个配置一般用不着，就不写描述了）
```yml
spring:
  dubbo: 
    services:
      - provider: 
        accesslog:
        async:
        cluster: 
        connections: 
        contextpath: 
        delay: 
        deprecated:
        document: 
        dynamic:
        executes: 
        filter: 
        group: 
        interface: 
        layer: 
        listener: 
        loadbalance: 
        mock:
        owner: 
        path: 
        protocol: 
        proxy: 
        ref:
        register:
        registry: 
        retries: 
        stub:
        timeout: 
        token:
        version: 
        weight:  
```
#### 10.调用者配置的列表（由于这个配置一般用不着，就不写描述了）
```yml
spring:
  dubbo: 
    references:
      - actives: 
        async:
        cache:
        check:
        client: 
        cluster: 
        connections: 
        filter: 
        generic:
        group: 
        id: 
        init:
        interface: 
        layer: 
        listener: 
        loadbalance: 
        mock:
        owner: 
        protocol: 
        proxy:
        registry: 
        retries: 
        stub:
        timeout: 
        url: 
        validation:
        version: 
```

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)