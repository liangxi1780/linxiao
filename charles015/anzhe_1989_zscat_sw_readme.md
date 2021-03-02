# zscat_sw
springboot dubbo redis solr mq kafka 商城 blog cms
 qq群 483681368
 
zscat


- ├── sw-common -- SSM框架公共模块
- ├── dubbo-cache-starter -- dubbo缓存插件
- ├── app-monitor --dubbo服务监控和统计
- ├── sw_manager -- 后台管理模板
- ├── sw-portl -- 官网门户展示
- ├── sw-search-- search管理系统（实现了luence，solr两种搜索）
- |    ├── search-api -- search相关的service
- |    ├── search-service -- search相关的service实现  dubbo服务
- |    ├── search-web -- search消费者 前端展示
- ├── sw-blog-- blog管理系统
- |    ├── blog-api -- blog相关的service
- |    ├── blog-service -- blog相关的service实现  dubbo服务
- |    ├── blog-web -- blog消费者 前端展示
- ├── sw-cms-- cms管理系统
- |    ├── cms-api -- cms相关的service
- |    ├── cms-service -- cms相关的service实现  dubbo服务
- |    ├── cms-web -- cms消费者 前端展示
- ├── sw-shop-- shop管理系统
- |    ├── shop-api -- shop相关的service
- |    ├── shop-service -- shop相关的service实现  dubbo服务
- |    ├── shop-web -- shop消费者 前端展示
- |    ├── shop-h5-- h5消费者 前端展示

1.项目部署，根据doc目录下的 zsboot.sql，weixin.sql，分别创建数据库，相关数据库配置 参考application.properties
先安装 spring-boot-starter-dubbo模块到本地
### 2.blog模块为例  



- a.启动blog-services下面的BlogServiceApplication主类，启动blog的dubbo服务
- b.启动blog-web下面的BlogWebApplication主类，访问 http://localhost:2001/front/blog/indexs
### 3.cms模块为例 
 


- a.启动cms-services下面的cmsServiceApplication主类，启动blog的dubbo服务
- b.启动cms-web下面的cmsWebApplication主类，访问 http://localhost:2001/web/cms/index http://localhost:2001/wap/cms/index
### 4.shop模块为例  



- a.启动shop-services下面的ShopServiceApplication主类，启动blog的dubbo服务
- b.启动shop-web下面的ShopWebApplication主类，访问  http://localhost:2007/front http://localhost:2007/youhong
- c.启动shop-h5下面的ShopWebApplication主类，访问 http://localhost:2006/wap1 
### 5.search模块为例
  


- a.启动search-services下面的SearchServiceApplication主类，启动blog的dubbo服务
- b.启动search-web下面的SearchWebApplication主类，访问 http://localhost:2008
### 6.启动sw_manager下面的 GunsApplication主类，访问 http://localhost  admin  111111
### 7.启动sw_portl下面的 PortlWebApplication主类，访问 http://localhost:2009/index



- [搜索模块具体介绍](http://git.oschina.net/catshen/zscat_sw/blob/master/sw-search/README.md)
- [后台管理具体介绍](http://git.oschina.net/catshen/zscat_sw/tree/master/sw_manager/README.md)
- [blog管理具体介绍](http://git.oschina.net/catshen/zscat_sw/tree/master/sw_blog/README.md)
- [cms管理具体介绍](http://git.oschina.net/catshen/zscat_sw/tree/master/sw_cms/README.md)
- [商城管理具体介绍](http://git.oschina.net/catshen/zscat_sw/tree/master/sw_shop/README.md)

请作者喝杯咖啡

![输入图片说明](https://git.oschina.net/uploads/images/2017/0829/203712_6694b4c1_134431.jpeg "weixin.jpg")
![输入图片说明](https://git.oschina.net/uploads/images/2017/0829/203723_5567bd56_134431.jpeg "alipay.jpg")

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)