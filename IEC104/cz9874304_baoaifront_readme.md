# BaoAI 小宝人工智能和量化系统
人工智能和量化从这开始

 
 
     
 
 
 
     
     
     
     
     
     
     
 

小宝人工智能和量化平台是简洁、直观、强大的前端和后端SPA开发框架，支持国际化，以模块为基础，让WEB应用、人工智能和量化系统开发更迅速、更简单。平台包含多个模块，主要包括基于角色的权限管理基础平台（用户、角色、权限、日志、附件、配置参数、分类管理）、通知模块、自动代码产生模块、任务系统模块、内容管理系统模块、网站模块、电子手册模块、人工智能模块、图像识别模块，人脸识别模块，金融数据采集模块，大数据模块，量化交易模块等。

## 功能特点：

+ 超10万行代码
+ 平台模块化，易于开发扩展
+ 前端兼容多种浏览器
+ 兼容性好，跨平台，响应式设计
+ 平台二次开发学习曲线低，易上手
+ 国际化
+ 前后端代码分离
+ 基于H5的单页面应用（SPA）
+ 自动代码产生器
+ 自动产生API文档及测试界面
+ 支持多数据库和数据迁移
+ 强大的富文本编辑
+ 人工智能
+ 大数据网络爬虫
+ 金融数据采集模块
+ 量化分析
+ 完善的开发和部署工具和方案

## 下载源码

BaoAI前后端分离框构，包含有前端项目和后端项目

+ 前端项目源码: [BaoAIFront](https://github.com/yuanbaonet/baoaifront) 

## 文档

+ 手册
    + [BaoAI 开发手册](http://www.baoai.co/web/book?id=50)
    + [BaoAI 前端开发手册](http://www.baoai.co/web/book?id=46)

+ 数据模拟API

   + 运行方式：gulp server , API服务文件：./mockAPI.js 。模拟数据：./data/**/*.json

+ 模块扩展

    + [模块](http://www.baoai.co/web/book?id=88)


## 前端开发工具

[Visual Studio Code](http://code.visualstudio.com)

安装插件：

`Chinese (Simplified) Language Pack for Visual Studio Code`

`jshint`

`git history`


## 项目前端 BaoAIFront 安装步骤

需要安装 [Node.js](https://nodejs.org) 

`使用bower下载第三方js库时，国内可能下载速度很慢，建议克隆 https://gitee.com/yuanbaonet/baoaifront.git  ，
直接解压源代码根路径下的bower_components.zip`

```shell
# 安装 bower:
npm install -g bower

# 安装 gulp
npm install -g gulp

# npm 安装第三方js
# 使用bower下载第三方js库时，国内可能下载速度很慢，可以直接解压源代码根路径下的bower_components.zip，此步可以跳过
bower install

# npm 安装依赖库:
npm install

# 运行前端代码方式一：自带数据模拟API，适合前端工程师
gulp server

# 运行前端代码方式二：Python全栈开发工程师
# 需要安装BaoAI后端
gulp serve

# 运行前端代码方式三：Python全栈开发工程师，反向代理(前后端共用相同地址和端口，仅目录不同)
# 需要安装BaoAI后端
gulp proxy

# 构建生产代码
gulp build

# 运行前端代码方式四：测试运行生产代码
# 需要安装BaoAI后端
gulp prod

```
构建的生产代码保存在 `dist` 目录.

## 项目代码自动产生模块

使用自动代码产生模块，可以使字段、模型、生成数据库、前端代码、后端代码和权限配置一并可视化完成，一般项目可以零代码实现。
该部份主要包括三个扩展模块： 数据迁移模块、自动代码模型模块和自动代码产生模块


## BaoAI 小宝人工智能和量化平台系统架构
 


## BaoAI 小宝人工智能和量化平台知识体系

可用于各行业的前端和后端系统软件开发、CMS、人工智能、图像识别、人脸识别、大数据和量化投资领域等。前后端分离SPA架构，使用AngularJS/Bootstrap等前端框架实现响应式和SPA程序设计，后端主要使用Python语言，主要包括如下框架：flask提供web服务，Jinja2提供模板服务，Numpy、Pandas、Scikit-Learn、Tensorflow和Keras等实现人工智能服务，celery实现任务调度，scrapy提供网络爬虫，基于Backtrader的金融量化服务等。

 

基于BaoAI设计案例：

内容管理网站：

 

管理系统后台：

 

人工智能：

 

量化系统：

 

## 帮助

+ Email [703264459@qq.com](703264459@qq.com) 


## 版权说明

Apache2.0

## 版权说明

 
  





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)