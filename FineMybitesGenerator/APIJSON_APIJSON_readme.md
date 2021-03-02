
 
  APIJSON
 
 
 🏆码云最有价值开源项目 🚀后端接口和文档自动化，前端(客户端) 定制返回JSON的数据和结构！ 

 
     
     
     
     
     
 
 
     
     
     
     
     
     
 
 
     
     
     
 
 
   English 
   通用文档 
   视频教程 
   在线工具 
 

 
   
 

---


APIJSON是一种专为API而生的 JSON网络传输协议 以及 基于这套协议实现的ORM库。 
为 简单的增删改查、复杂的查询、简单的事务操作 提供了完全自动化的API。 
能大幅降低开发和沟通成本，简化开发流程，缩短开发周期。 
适合中小型前后端分离的项目，尤其是 BaaS、Serverless、互联网创业项目和企业自用项目。 

通过自动化API，前端可以定制任何数据、任何结构！ 
大部分HTTP请求后端再也不用写接口了，更不用写文档了！ 
前端再也不用和后端沟通接口或文档问题了！再也不会被文档各种错误坑了！ 
后端再也不用为了兼容旧接口写新版接口和文档了！再也不会被前端随时随地没完没了地烦了！

 
     
 


### 特点功能

#### 在线解析
* 自动生成接口文档，清晰可读永远最新
* 自动校验与格式化，支持高亮和收展
* 自动生成各种语言代码，一键下载
* 自动管理与测试接口用例，一键共享
* 自动给请求JSON加注释，一键切换

#### 对于前端
* 不用再向后端催接口、求文档
* 数据和结构完全定制，要啥有啥
* 看请求知结果，所求即所得
* 可一次获取任何数据、任何结构
* 能去除重复数据，节省流量提高速度

#### 对于后端
* 提供通用接口，大部分API不用再写
* 自动生成文档，不用再编写和维护
* 自动校验权限、自动管理版本、自动防SQL注入
* 开放API无需划分版本，始终保持兼容
* 支持增删改查、模糊搜索、正则匹配、远程函数等

 

![](https://raw.githubusercontent.com/TommyLemon/StaticResources/master/APIJSON_Auto_get.jpg) 
 
   多表关联查询、结构自由组合、多个测试账号、一键共享测试用例 
 

![](https://raw.githubusercontent.com/TommyLemon/StaticResources/master/APIJSON_Auto_code.jpg) 
 
   自动生成封装请求JSON的Android与iOS代码、一键自动生成JavaBean或解析Response的代码 
 

![](https://raw.githubusercontent.com/TommyLemon/StaticResources/master/APIJSON_Auto_doc.jpg) 
 
   自动保存请求记录、自动生成接口文档，可添加常用请求、快捷查看一键恢复 
 

![](https://raw.githubusercontent.com/TommyLemon/StaticResources/master/APIJSON_Auto_test.jpg) 
 
   一键自动接口回归测试，不需要写任何代码(注解、注释等全都不要) 
 

![](https://raw.githubusercontent.com/TommyLemon/StaticResources/master/APIJSON_Auto_summary.jpg) 
 
   一图胜千言 - 部分基础功能概览 
 

  
[以下Gif图看起来比较卡，实际在手机上App运行很流畅]
 
![](https://raw.githubusercontent.com/TommyLemon/StaticResources/master/APIJSON_App_MomentList_Circle.gif) 
![](https://raw.githubusercontent.com/TommyLemon/StaticResources/master/APIJSON_App_Moment_Name.gif) 
![](https://raw.githubusercontent.com/TommyLemon/StaticResources/master/APIJSON_App_Moment_Comment.gif)

 


### 为什么要用APIJSON？
[前后端 关于接口的 开发、文档、联调 等 10 大痛点解析](https://github.com/TommyLemon/APIJSON/wiki)


### 常见问题
#### 1.如何定制业务逻辑？
在后端编写 远程函数，可以拿到 session、version、当前 JSON 对象、参数名称 等，然后对查到的数据自定义处理  
https://github.com/APIJSON/APIJSON/issues/101

#### 2.如何控制权限？
在 Access 表配置校验规则，默认不允许访问，需要对 每张表、每种角色、每种操作 做相应的配置，粒度细分到 Row 级  
https://github.com/APIJSON/APIJSON/issues/12

#### 3.如何校验参数？
在 Request 表配置校验规则 structure，提供 NECESSARY、TYPE、VERIFY 等通用方法，可通过 远程函数 来完全自定义  
https://github.com/APIJSON/APIJSON/wiki#%E5%AE%9E%E7%8E%B0%E5%8E%9F%E7%90%86

 
其它问题见 Closed Issues  
https://github.com/APIJSON/APIJSON/issues?q=is%3Aissue+is%3Aclosed


### 快速上手

#### 1.后端部署
可以跳过这个步骤，直接用APIJSON服务器IP地址 apijson.cn:8080 来测试接口。 
见&nbsp; [APIJSON后端部署 - Java](https://github.com/TommyLemon/APIJSON/tree/master/APIJSON-Java-Server) 

#### 2.前端部署
可以跳过这个步骤，直接使用 [APIAuto-自动化接口管理工具](https://github.com/TommyLemon/APIAuto) 或 下载客户端App。 
见&nbsp; [Android](https://github.com/TommyLemon/APIJSON/tree/master/APIJSON-Android) &nbsp;或&nbsp; [iOS](https://github.com/TommyLemon/APIJSON/tree/master/APIJSON-iOS) &nbsp;或&nbsp; [JavaScript](https://github.com/TommyLemon/APIJSON/tree/master/APIJSON-JavaScript) 


### 下载客户端App

仿微信朋友圈动态实战项目 
[APIJSONApp.apk](http://files.cnblogs.com/files/tommylemon/APIJSONApp.apk)

测试及自动生成代码工具 
[APIJSONTest.apk](http://files.cnblogs.com/files/tommylemon/APIJSONTest.apk)


### 使用登记
 
     
     
     
     
     
     
     
     
     
     
 

[更多 APIJSON 使用者](https://github.com/TommyLemon/APIJSON/issues/73)


### 贡献者们
 
     
     
     
     
     
     
     
     
     
     
     
     
   
     
     
     
     
     
     
     
     
     
 
 
感谢大家的贡献。


### 规划及路线图
https://github.com/APIJSON/APIJSON/blob/master/Roadmap.md


### 我要赞赏
如果你喜欢 APIJSON，感觉 APIJSON 帮助到了你，可以点右上角 ⭐Star 支持一下，谢谢 ^_^  
你也还可以扫描下面的二维码，赞助点服务器和域名的购买及维护费用，或者请作者喝一杯咖啡~

  

> 如果希望捐赠之后能获得相关的帮助，可以选择加入下面的付费群来取代普通捐赠，可以获得作者的直接帮助。

如果在捐赠留言中备注名称，将会被记录到列表中~ 如果你也是 Github 开源作者， 
捐赠时可以留下 Github 项目地址或者个人主页地址，链接将会被添加到列表中起到互相推广的作用。


### 技术交流
如果有什么问题或建议可以 [提ISSUE](https://github.com/TommyLemon/APIJSON/issues) 或 加群，交流技术，分享经验。 
如果你解决了某些bug，或者新增了一些功能，欢迎 [贡献代码](https://github.com/TommyLemon/APIJSON/pulls)，感激不尽~

#### QQ解决群 - 607020115（付费）
自开群以来，还是有很多的朋友提出了很多问题，我也解决了很多问题，其中有大半问题是本库的Bug导致，也有些是使用者项目本
身的环境问题，这花费了我大量的时间，经过我的观察和测试，到目前为止，本库的bug已经越来越少，当然不能说完全没有，但是
已经能满足很大部分项目的需求。所以从现在起，我做出一个决定：把之前的讨论群改成解决群，并开启付费入群功能，专为解决大
家在使用本库时遇到的问题，不管是本库bug还是特殊的项目环境导致（包含项目本身的bug）。
我也有自己的工作和娱乐时间，只有大家理解和支持我，我才能专心的为大家解决问题。不过也不用担心，我已经建立了另一个可以免费
进入的QQ讨论群。

#### QQ讨论群 - 734652054（免费）
这个群，免费进入，大家可以相互讨论本库的相关使用和出现的问题，群主也会在里面解决问题，如果提出的问题，群成员不能帮助
解决，需要群主解决，但是要花费群主五分钟以上的时间（本库Bug除外），群主将不会解决这个问题，如果项目紧急，请付费进入解
决群解决（不过注意，付费群中群主会很认真很努力的解决问题，但也不能保证已经能完美解决）或者转换使用其他的开源库。


### 相关推荐
[APIJSON, 让接口和文档见鬼去吧！](https://my.oschina.net/tommylemon/blog/805459)

[仿QQ空间和微信朋友圈，高解耦高复用高灵活](https://my.oschina.net/tommylemon/blog/885787)

[后端开挂:3行代码写出8个接口！](https://my.oschina.net/tommylemon/blog/1574430)

[后端自动化版本管理，再也不用改URL了！](https://my.oschina.net/tommylemon/blog/1576587)

[3步创建APIJSON后端新表及配置](https://my.oschina.net/tommylemon/blog/889074)

[APIJSON 自动化接口和文档的快速开发神器 （一）](https://blog.csdn.net/qq_41829492/article/details/88670940)

[APIJSON在mac电脑环境下配置去连接SQL Server](https://juejin.im/post/5e16d21ef265da3e2e4f4956)

[APIJSON复杂业务深入实践（类似12306订票系统）](https://blog.csdn.net/aa330233789/article/details/105309571)


### 生态项目
[APIAuto](https://github.com/TommyLemon/APIAuto) 机器学习测试、自动生成代码、自动静态检查、自动生成文档与注释等，做最先进的接口管理工具

[UnitAuto](https://github.com/TommyLemon/UnitAuto) 机器学习自动化单元测试平台，零代码、全方位、自动化 测试 方法/函数 的正确性和可用性

[apijson-doc](https://github.com/vincentCheng/apijson-doc) APIJSON 官方文档，提供排版清晰、搜索方便的文档内容展示，包括设计规范、图文教程等

[APIJSONdocs](https://github.com/ruoranw/APIJSONdocs) APIJSON 英文文档，提供排版清晰的文档内容展示，包括详细介绍、设计规范、使用方式等

[apijson.org](https://github.com/APIJSON/apijson.org) APIJSON 官方网站，提供 APIJSON 的 功能简介、登记用户、作者与贡献者、相关链接 等

[APIJSON.NET](https://github.com/liaozb/APIJSON.NET) C# 版 APIJSON ，支持 MySQL, PostgreSQL, SQL Server, Oracle, SQLite

[apijson-php](https://github.com/qq547057827/apijson-php) PHP 版 APIJSON，基于 ThinkPHP，支持 MySQL, PostgreSQL, SQL Server, Oracle 等

[apijson-node](https://github.com/kevinaskin/apijson-node) Node.ts 版 APIJSON，提供 nestjs 和 typeorm 的 Demo，支持 MySQL, PostgreSQL, SQL Server, Oracle

[uliweb-apijson](https://github.com/zhangchunlin/uliweb-apijson) Python 版 APIJSON，支持 MySQL, PostgreSQL, SQL Server, Oracle, SQLite 等

[APIJSON](https://github.com/crazytaxi824/APIJSON) Go 版 APIJSON，功能开发中...([不可用且长期未更新，期待热心开发者帮助完善或新增项目](https://github.com/APIJSON/APIJSON/issues/111))

[APIJSONKOTLIN](https://github.com/luckyxiaomo/APIJSONKOTLIN) Kotlin 版 APIJSON，基础框架搭建中...(不可用且长期未更新，期待热心开发者帮助完善或新增项目)

[APIJSONParser](https://github.com/Zerounary/APIJSONParser) 第三方 APIJSON 解析器，将 JSON 动态解析成 SQL

[ApiJsonByJFinal](https://gitee.com/zhiyuexin/ApiJsonByJFinal) 整合 APIJSON 和 JFinal 的 Demo

[SpringServer1.2-APIJSON](https://github.com/Airforce-1/SpringServer1.2-APIJSON) 智慧党建服务器端，提供 上传 和 下载 文件的接口

[AbsGrade](https://github.com/APIJSON/AbsGrade) 列表级联算法，支持微信朋友圈单层评论、QQ空间双层评论、百度网盘多层(无限层)文件夹等

[APIJSON-Android-RxJava](https://github.com/TommyLemon/APIJSON-Android-RxJava) 仿微信朋友圈动态实战项目，ZBLibrary(UI) + APIJSON(HTTP) + RxJava(Data)

[Android-ZBLibrary](https://github.com/TommyLemon/Android-ZBLibrary) Android MVP快速开发框架，Demo全面，注释详细，使用简单，代码严谨


感谢热心的作者们的贡献，点 ⭐Star 支持下他们吧。


### 持续更新
[https://github.com/TommyLemon/APIJSON/commits/master](https://github.com/TommyLemon/APIJSON/commits/master)

### 码云主页
https://gitee.com/TommyLemon/APIJSON


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)