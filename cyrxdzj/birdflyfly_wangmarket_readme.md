# wangmarket网市场云建站系统，结合各种产品，将建站成本降低到1块钱！打破传统建站的高成本，让价格不再是阻碍的门槛，让每个人都能有自己的网站！ [www.wang.market](http://www.wang.market) ## 导航|[官网](http://www.wang.market/)  | [模版库](http://wang.market/template.jsp) | [升级日志](http://www.wang.market/log.html) | [Api接口](http://www.wang.market/wangmarket_api.html) | [快速安装](http://www.wang.market/2725.html) |
| ------------- |:-------------:| -----:|-----:|-----:|
| | [模版(备)](http://www.wang.market/template.html) |v3.8.1|  |  |## 功能简介1. 在线开通网站2. 自动分配二级域名3. 在线绑定域名4. (半)可视化界面编辑5. 成熟的云端模版库一键导入创建网站6. 网站页面100%全部自定义的模版体系7. 承载几百到几十万的网站个数8. 极速做网站的效率(导入模版－改图改字－上线)9. 价格真的可以达到1个网站几块钱！10. ………………[更多可查看](http://www.wang.market/index.html#services) ## 在线快速体验##### CMS模式网站管理后台（另外还有[纯傻瓜化操作后台的手机模式、电脑模式](http://www.wang.market/index.html#about)）登录网址：[wang.market](http://wang.market) 登录帐号：ceshicms 登录密码：ceshicms ##### 代理后台，可自由开通、管理网站登录网址：[wang.market](http://wang.market) 登录帐号：ceshidaili 登录密码：ceshidaili  ## 项目简介 网市场云建站系统，于09年开发wap系统建站。之后在xnx3、iw等基础上开发而来。 于15年重新启动， 16年开始试运行 17年底正式开源发布！ 截止17年底： 共建立网站服务客户一千余个，经过市场及客户验证。而非一时兴起作出来扔网上开源后就不管的 svn版本更新迭代837次！ 版本功能性升级57次！[升级日志](http://www.wang.market/log.html)  ## 运行环境 语言：Java 1.8 数据库：Mysql 5.5 运行容器：Tomcat8 运行环境：Linux (Mac开发，未再Windows下实验)  ## 项目极速搭建体验步骤##### 1. 下载应用程序运行程序在 [/application/wangmarket.zip](https://github.com/xnx3/wangmarket/application/wangmarket.zip) 下载后解压缩，解压后的文件可直接丢到tomcat8中 ##### 2. 配置数据库连接数据库SQL文件： [wangmarket.sql](https://github.com/xnx3/wangmarket/blob/master/wangmarket.sql) 可新建一个数据库后直接将其导入。 修改数据库的配置文件： /WEB-INF/classes/db.properties ##### 3. 执行安装数据库配置好后，将项目运行起来，访问项目 /install/index.do 进行下一步下一步安装 ##### 4. 登陆体验登陆地址为 /login.do 登陆账号密码都是 ceshicms 另，附带10分钟视频说明，让你10分钟就会基本使用。[视频点此查看](https://v.qq.com/x/page/k0516y0fouw.html)  [注意，请查看详细安装步骤及注意事项：/else/quickConfig.md](https://github.com/xnx3/wangmarket/blob/master/else/quickConfig.md) [配置文档说明（可不用看）:/else/instructions.md](https://github.com/xnx3/wangmarket/blob/master/else/instructions.md)  ## 云端模版库 你的时间是非常宝贵的！不会让你一接触就要自己去学习做模版。我们附带有 [云端模版库，点此查看](http://wang.market/template.jsp) 虽然模版不多只有不到20套，但却是可以在创建网站后一键导入，直接拿过来使用！一键导入之后，会自动创建栏目、页面。你只需要改一下栏目名字、改改文字、图片，就可以达到成本网站交付标准！作为初期的你，足够用此来来服务客户、及熟悉整个系统！另外我们的模版库的模版会持续增加。 
[所见网站，皆可为我所用－无限模版计划](https://github.com/xnx3/templatespider) ## 使用的成本投入#### 1. 无成本 如果你只是需要一个两个网站，不需要费这么大的劲熟悉程序购买服务器搭建等。可直接在线开通网站 [http://wang.market/regByPhone.do](http://wang.market/regByPhone.do?inviteid=50) 无任何广告，可永久使用。让人人都能有网站！ #### 2. 七百左右成本 一台1核2G，安装网市场云建站系统，可以支撑起至少200个以上的网站(也可能过1000个没啥问题。网站本身做好后就很少会登陆后台修改了)。服务器成本一年大约七百。 #### 3. 六千以上的成本 购买两台及以上，配置为2核4G及以上的云服务器。采用负载均衡、OSS、RDS、Docker、MQ、SLS、及弹性伸缩方案，将网站访问、管理后台、客服等功能完全分离，一年预计最低消耗六千元以上。建立十来万个网站不在话下。此种方式架构部署如下： ![](http://cdn.weiunity.com/site/341/templateimage/4f6088b65e514321a7caed3c1f62a547.png)  

## 当前目录结构```
wangmarket                          GitHub目录
├─SourceCode                        项目源代码
│  ├─admin                          管理后台(网站管理后台、总管理后台、代理后台)(Web Project)
│  ├─domain                         域名解析绑定(用于分配或绑定的域名访问网站)(Web Project)
│  └─im                             IM客服(在线客服功能)(Web Project)
├─application                       可直接运行的应用(下载后可直接部署起来运行)
│  ├─wangmarket.zip                 网市场运行包，解压后放进tomcat即可运行
│  └─domian.zip                     还没有...待加入的
├─else                              其他的相关文件
│  ├─upgradeLog                     自项目上线运营后的升级日志
│  ├─pc_wap_tag                     手机、电脑模式网站模版所使用的动态标签
│  └─instructions.md                其他项目配置说明，如邮件发送、日志系统等
└─wangmarket.sql                    项目运行所需要的数据库文件(Mysql数据库)
```## 具体应用目录结构```Source/admin/ 管理后台(网站管理后台、总管理后台、代理后台)
├─WebRoot                 
│  ├─WEB-INF               
│  │  ├─inputModel            CMS模式网站的默认输入模型
│  │  ├─lib                   项目所依赖的jar包
│  │  ├─template              wap、pc模式网站的模版
│  │  ├─view                  Spring MVC 的view展示层
│  │  └─urlrewrite.xml        伪静态配置文件
│  ├─module                   其他三方模块
│  ├─template.jsp             模版浏览，模版页面
│  ├─index.html               入口页面，如果此项目也用于域名解析绑定使用，此页面是必须要存在的
│  └─module                   插件数据如安装卸载脚本目录
├─src
│  ├─com        
│  │  │─xnx3         
│  │  │  ├─admin              网站管理后台
│  │  │  ├─domain             域名解析绑定(即网站访问)
│  │  │  ├─im                 IM在线客服
│  │  │  ├─j2ee               IW框架相关
│  │  └──└─superadmin         总管理后台、代理后台
└──└─db.properties            数据库配置文件

```## 交流、反馈 开发者姓名：管雷鸣 开发者QQ：921153866 开发者微信：xnx3com 开发者微信公众号：wangmarket 交流QQ群：472328584 官方网站：[www.wang.market](http://www.wang.market) GitHub：[github.com/xnx3/wangmarket](https://github.com/xnx3/wangmarket) 开源中国：[gitee.com/mail_osc/wangmarket](https://gitee.com/mail_osc/wangmarket)  ## 作者简介 对网站这种普惠全民的事，有极大的热爱。又或者说，对于能改变什么，有强烈的兴致。 高一接触网吧认识电脑，高二接触到网站(UBB标签排版那种)，高三辍学自学HTML、PHP，然后进入四大名校之新华电脑。 入校期间开始用新学的Java自写建站系统，1年毕业，毕业半年后，于2011年2月，将自己写的最初版本的WAP手机建站系统发布到了 [中国站长站](http://down.chinaz.com/soft/29191.htm) [功能说明](http://www.xnx3.com/software/xxJspMql/20121102/8.html) 而后发布了多项开发包，如  [Java的辅助开发包](https://github.com/xnx3/xnx3) ，找图找色模拟键盘按键鼠标点击，  [iw web快速开发架构](https://github.com/xnx3/iw) 集成了权限、会员、日志、支付等常用项目的功能于一体，适用于有什么新项目可以直接拿来做新功能即可，简化开发时的重复工作。 而网市场云建站系统，便是在以上产品的基础上而来。  ## 版权声明 著作权登记号：2017SR608214 本软件使用 Apache License 2.0 协议。您可以随意修改、发布，或用于商业领域。但首页底部需保留我们“网市场”版权标示及链接！ 另外可以与我们有更多合作可以查看： [http://www.wang.market/index.html#join](http://www.wang.market/index.html#join)    项目由个人历经数年，凭借每晚四小时开发而来。一个人的兴趣、执念、或者信仰，所发挥出的光芒，可能会照亮一个行业 

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)