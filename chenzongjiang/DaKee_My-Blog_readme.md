# My Blog

My Blog是由Docker+SpringBoot+Mybatis+thymeleaf等技术实现的Java博客系统，博客模板是[@biezhi](https://github.com/biezhi)大神的开源项目[tale](https://github.com/otale/tale)，本来是一个docker和springboot的实战练习项目，目前已经开源，功能齐全、部署简单及完善的代码，一定会给使用者无与伦比的体验，如果觉得这个项目不错，请为它[点赞](https://github.com/ZHENFENG13/My-Blog/stargazers)支持。

- **你可以拿它作为博客模板，因为My Blog界面十分美观简洁，满足私人博客的一切要求；**
- **你也可以把它作为springboot技术的学习项目，My Blog也足够符合要求，且代码和功能完备；**
- **你还可以将其视为一个docker技术的练手教程，体验和使用红极一时的虚拟容器技术，My Blog中脚本和文档十分完善并且持续更新。**

#### tips

- **数据库文件目录为```docker-extension/mysql/schema.sql```；**
- **部署后你可以根据自己需求修改版权文案、logo图片、备案记录等信息；**
- **My Blog还有许多不完善的地方，鄙人才疏学浅，望见谅！**

演示站点：http://13blog.site

[![Build Status](https://travis-ci.org/ZHENFENG13/My-Blog.svg?branch=master)](https://travis-ci.org/ZHENFENG13/My-Blog)
![Version 3.2.0](https://img.shields.io/badge/version-3.2.0-yellow.svg)
[![License](https://img.shields.io/badge/license-apache-blue.svg)](https://github.com/ZHENFENG13/My-Blog/blob/master/LICENSE)

#### 宣传

十三近期于CSDN上传了一份自己制作的达人课课程,感兴趣的朋友可以看一下：

* [x] [GitChat达人课-SSM搭建精美实用的管理系统](https://gitbook.cn/gitchat/column/5b4dae389bcda53d07056bc9)

![gitchat](https://raw.githubusercontent.com/ZHENFENG13/resource/master/images/2018-07-19/gitchat.png)

#### 相关博客文章

* [x] [Docker+SpringBoot+Mybatis+thymeleaf的Java博客系统开源啦](http://www.cnblogs.com/han-1034683568/p/6840493.html)
* [x] [My-Blog搭建过程：如何让一个网站从零到可以上线访问](http://www.cnblogs.com/han-1034683568/p/6885545.html)
* [x] [利用Dockerfile构建mysql镜像并实现数据的初始化及权限设置](http://www.cnblogs.com/han-1034683568/p/6941337.html)
* [x] [Java开源博客My-Blog之docker容器组件化修改](http://www.cnblogs.com/han-1034683568/p/7102765.html)
* [x] [Java开源博客My-Blog之mysql容器重复初始化的严重bug修复过程](http://www.cnblogs.com/han-1034683568/p/7231895.html)
* [x] [Springboot与Thymeleaf模板引擎整合基础教程](http://www.cnblogs.com/han-1034683568/p/7520012.html)
* [x] [thymeleaf模板引擎调用java类中的方法](http://www.cnblogs.com/han-1034683568/p/7527564.html)

#### 捐赠

**网站的持续运行需要各项基础设施的搭建，而服务期的续费和维护及各种配套服务的购买也需要一定的费用，希望朋友们给予一点支持，谢谢！**

**支付宝：** **微信支付：** 

# Quick Start

* [x] [1.如何部署My Blog](https://github.com/ZHENFENG13/My-Blog/wiki/1-%E5%A6%82%E4%BD%95%E9%83%A8%E7%BD%B2My-Blog)
 - [1.0 基础环境搭建](https://github.com/ZHENFENG13/My-Blog/wiki/1.0-%E5%9F%BA%E7%A1%80%E7%8E%AF%E5%A2%83)
 - [1.1 安装Docker环境](https://github.com/ZHENFENG13/My-Blog/wiki/1.1-安装Docker环境)
 - [1.2 安装docker-compose](https://github.com/ZHENFENG13/My-Blog/wiki/1.2-%E5%AE%89%E8%A3%85docker-compose)
* [x] [2.通过共享镜像直接部署My Blog](https://github.com/ZHENFENG13/My-Blog/wiki/2-%E9%80%9A%E8%BF%87%E5%85%B1%E4%BA%AB%E9%95%9C%E5%83%8F%E7%9B%B4%E6%8E%A5%E9%83%A8%E7%BD%B2My-Blog)
* [x] [3.1 非docker环境运行My Blog](https://github.com/ZHENFENG13/My-Blog/wiki/3.1-%E9%9D%9Edocker%E7%8E%AF%E5%A2%83%E8%BF%90%E8%A1%8CMy-Blog)
* [x] [3.2 将My Blog部署到tomcat(非docker环境)](https://github.com/ZHENFENG13/My-Blog/wiki/3.2-%E5%B0%86My-Blog%E9%83%A8%E7%BD%B2%E5%88%B0tomcat(%E9%9D%9Edocker%E7%8E%AF%E5%A2%83))
* [x] [4.开发环境运行代码](https://github.com/ZHENFENG13/My-Blog/wiki/4-%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E8%BF%90%E8%A1%8C%E4%BB%A3%E7%A0%81)
* [x] [5.博客上线及备案相关流程](https://github.com/ZHENFENG13/My-Blog/wiki/%E4%B8%8A%E7%BA%BF%E5%8F%8A%E5%A4%87%E6%A1%88%E7%9B%B8%E5%85%B3)

[**常见问题**](https://github.com/ZHENFENG13/My-Blog/wiki/%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)

# Preview

**博客展示页1：**
![My Blog](https://raw.githubusercontent.com/ZHENFENG13/resource/master/images/2018-06-13/my-blog-2.gif)
**博客展示页2：**
![My Blog](https://raw.githubusercontent.com/ZHENFENG13/resource/master/images/2018-06-13/my-blog-1.gif)
**登录页：**
![登录页](http://images2015.cnblogs.com/blog/859549/201705/859549-20170511122916004-738411708.png)
**My Blog后台：**
![My Blog](https://raw.githubusercontent.com/ZHENFENG13/resource/master/images/2018-06-13/My-Blog-admin-1.gif)
**My Blog后台：**
![My Blog](https://raw.githubusercontent.com/ZHENFENG13/resource/master/images/2018-06-13/My-Blog-admin-2.gif)

# Log

2017-03-27 添加docker整合 
2017-03-28 schema.sql修改 
2017-03-28 install步骤，数据库地址配置时:mysql地址写为mysql容器的名字即可,即mysql:3306 
2017-03-29 修复添加评论时空指针异常的bug 
2017-03-30 添加预览功能,限制文章浏览，如果为草稿状态前端即使通过正确的url也不能浏览 
2017-03-31 文章浏览数不变的bug,后期浏览数及评论这些参数放到缓存里去 
2017-04-01 添加druid数据源 
2017-04-02 重写mysql的Dockerfile文件，修改install过程 
2017-04-15 bug修复,footer样式调整 
2017-04-17 logo文件修改,附件上传功能 
2017-04-18 评论功能及页面修改 
2017-04-20 域名及网站的公网备案 
2017-04-25 docker-compose实现多容器部署 
2017-05-09 删除原install过程,改为脚本自动部署及初始化 
2017-05-10 docker容器时区不同步问题修复,文件整理 
2017-05-11 文件整理,排版和文案修改 
2017-05-13 正式上线啦 
2017-05-15 部署文档 
2017-05-21 My-Blog上线过程记录 
2017-06-30 目录调整:docker组件化 
2017-07-20 问题修复:docker-compose重启时mysql容器中数据被删除并初始化的问题 


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)