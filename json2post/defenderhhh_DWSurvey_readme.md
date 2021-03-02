# DWSurvey 调问表单问卷系统

DWSurvey是一款方便、高效、实用的调研问卷系统，一款基于 JAVA WEB 的开源问卷表单系统。

![DWSurveyDesign](http://file.diaowen.net/images/gif/dwsurvey-2.gif)


## 演示地址

[http://www.diaowen.net](http://www.diaowen.net)

    用户名：service@diaowen.net  密码: 123456

## 安装

因为DWSurvey是基于JAVA WEB实现，所以安装与一般的JAVA WEB程序无异，配置好数据库地址就可以正常使用。

### 安装说明

	服务器必须安装由 JAVA 1.6+、MySQL、Apache Tomcat 构成的环境

	由于引用的外部jar在你本地maven仓库中可能没有，这时只要您本地有maven环境，执行下bin目录下面的文件就可以自动导入。

## 环境配置说明

    lib目录下的几个jar包可能是您中央仓库没有，所以运行时如果提示找不到相关jar

    就请到bin目录下去执行jar导入命命，安装中央仓库缺失jar

    可直接执行 install-lose-jar.sh/install-lose-jar.bat

### 配置说明、数据初始化

先在您mysql中创建一个名为diaowen的数据库，然后导入/src/main/resources/conf/sql/目录下的dwsurvey.sql数据库脚本文件

配置文件地址

conf/application.properties

	#database settings
	jdbc.url=jdbc:mysql://localhost:3306/diaowen?useUnicode=true&characterEncoding=utf8
	jdbc.username=root
	jdbc.password=123456,.

分别修改```jdbc.url、jdbc.username、jdbc.password```

### 启动访问

配置完成后，启动服务在浏览器中输入如```localhost:8080/dwsurvey```相应的地址看到登录页面，表示已经安装成功。

如下图

## 特色

### 全新体验、流程简单

![pic](http://diaowenwebfile.oss-cn-shenzhen.aliyuncs.com/images/gif/newUi.png)

以一种全新的设计体验，告别繁琐的设计流程，通过简单有趣的方式，轻轻松松完成问卷设计，多种问卷样式模板选择，只为显现更精美的表单问卷.

### 丰富的题型 

丰富的题型支持，通过拖拽即可完成题目选择，并可以随意拖动其位置，还可置入所需图片、企业LOGO、设置答题逻辑，一份优美的问卷就是这么简单。

### 问卷表单静态化

对于问卷表单系统，因为所有的表单字段都是后台数据库来维护，所以对于每一次答卷请求，如果都从后端数据库去取每一题及选项的话，必定会对性能造成不小影响。

所以在发布的表单问卷时会对数据进行的页面静态化，生成一个真实的表单存档。

## 有问题怎么办？

对于调问网问卷系统安装及使用的问题，可以在用户交流群里，向作者或其它同学提问。

调问网交流QQ群：635994795

## 源代码发布

github: https://github.com/wkeyuan/DWSurvey

oschina: http://git.oschina.net/wkeyuan/DWSurvey

## 开源协议

DWSurvey以宽通用公共许可证LGPL3.0为开源协议，更好的支持商业使用环境！

- - -

## 关于调问网

没事喜欢瞎折腾，业余时间也想做点有意思的事情，同时对产品也比较感兴趣，一翻调研之后就决定来做个问卷系统。
于是便利用业余时间来做这款问卷表单平台，因为在2012的时候，国内的问卷系统都还比较初级，问卷设计流程复杂，页面也不美观。
所以就开始边调研、边画原型、边写前后端代码，最初的想法是一定要好用美观，在这之后的一年里就不断的设计开发，前前后后修改过3个大版本，现在开源的3.0版是在2013年9月份完成的。

- - -

## 作者

 柯远 ```keyuan258@gmail.com```

### 谢谢您的支持

 觉得不错就点下右上角的star，随时关注我们的动态，非常感谢！


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)