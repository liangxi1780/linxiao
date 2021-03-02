# J2Cache —— 基于内存和 Redis 实现的两级 Java 缓存框架


J2Cache 是 OSChina 目前正在使用的两级缓存框架。第一级缓存使用内存(同时支持 Ehcache 2.x、Ehcache 3.x 和 Caffeine)，第二级缓存使用 Redis 。
由于大量的缓存读取会导致 L2 的网络成为整个系统的瓶颈，因此 L1 的目标是降低对 L2 的读取次数。
该缓存框架主要用于集群环境中。单机也可使用，用于避免应用重启导致的缓存冷启动后对后端业务的冲击。

J2Cache 已经有 Python 语言版本了，详情请看 [https://gitee.com/ld/Py3Cache](https://gitee.com/ld/Py3Cache)

J2Cache 从 1.3.0 版本开始支持 JGroups 和 Redis Subscribe 两种方式进行缓存事件的通知。在某些云平台上可能无法使用 JGroups 组播方式，可以采用 Redis 发布订阅的方式。详情请看 j2cache.properties 配置文件的说明。

视频介绍：http://v.youku.com/v_show/id_XNzAzMTY5MjUy.html  
该项目提供付费咨询服务，详情请看：https://zb.oschina.net/market/opus/12_277

J2Cache 的两级缓存结构

L1： 进程内缓存(ehcache)   
L2： Redis 集中式缓存

由于大量的缓存读取会导致 L2 的网络带宽成为整个系统的瓶颈，因此 L1 的目标是降低对 L2 的读取次数

		 
## 数据读取

1. 读取顺序  -> L1 -> L2 -> DB

2. 数据更新

    1 从数据库中读取最新数据，依次更新 L1_1 -> L2 ，广播清除某个缓存信息  
    2 接收到广播（手工清除缓存 & 一级缓存自动失效），从 L1\_2 中清除指定的缓存信息

## J2Cache 配置

配置文件位于 core/resources 目录下，包含三个文件：

* ehcache.xml Ehcache 的配置文件，配置说明请参考 Ehcache 文档
* j2cache.properties J2Cache 核心配置文件，可配置 Redis 服务器、连接池以及缓存广播的方式
* network.xml JGroups 网络配置，如果使用 JGroups 组播的话需要这个文件，一般无需修改

实际使用过程需要将这三个文件复制到应用类路径中，如 WEB-INF/classes 目录。

J2Cache 运行时所需 jar 包请查看 core/pom.xml

## 测试方法

1. 安装 Redis  
2. 修改 `core/resource/j2cache.properties` 配置使用已安装的 Redis 服务器
3. 在命令行中执行 `mvn package -DskipTest=true` 进行项目编译  
4. 打开多个命令行窗口，同时运行 `runtest.sh` 
5. 在 > 提示符后输入 help 查看命令，并进行测试

## Maven 支持 

```
 
   net.oschina.j2cache   
   j2cache-core   
   2.2.0-beta   
 
```
## 示例代码

请看 [J2CacheCmd.java](https://gitee.com/ld/J2Cache/blob/master/core/src/net/oschina/j2cache/J2CacheCmd.java)

## 常见问题

1. J2Cache 的使用场景是什么？  
首先你的应用是允许在集群环境，使用 J2Cache 可以有效降低节点间的数据传输量
2. 为什么不能在程序中设置缓存的有效期  
在程序中定义缓存数据的有效期会导致缓存不可控，一旦数据出问题无从查起，因此 J2Cache 的所有缓存的有效期都必须在 ehcache 的配置中预设好再使用

## 哪些项目在用 J2Cache ？

* www.oschina.net
* https://gitee.com/jfinal/jfinal
* https://gitee.com/fuhai/jboot
* https://gitee.com/tywo45/t-io
* 更多项目收集中，如果你的项目用了，请告诉我

## TODO ##

* 增加使用 API 对 J2Cache 进行初始化配置

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)