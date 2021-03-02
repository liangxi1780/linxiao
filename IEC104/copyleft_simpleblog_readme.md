﻿## Django1.7开发一个简单的博客系统

#### 三个分支：

* master： 主分支
* py27：   基于python2.7.8版本的分支
* py34：   基于python3.4.2版本的分支

------------------------------------------
## 教程地址：
http://my.oschina.net/yidao620c/blog/343174
------------------------------------------

通过上面的教程，相信你已经搭建了一个具有基本功能的博客。最近在此基础之上又持续不断的改进，目前发布了1.0版本。
具体新增功能如下：

1. 页面美化，加入了自定义样式和最新bootstrap
2. 文章评论功能，并且显示每篇文章的评论数
3. 文章标签，侧边栏会显示标签云，具体还有一个实现标签云的算法
4. 分类目录
5. 最新文章，评论列表的显示
6. 文章归档功能，按照月份归档
7. 实现热门文章功能，根据点击率来排名
8. 文章的分页显示，每页大小可后台设置
9. 给文章评分，顶和踩
10. 集成xadmin的后台管理系统，管理员维护博客。
11. 全文搜索功能
12. 引入富文本编辑器，让格式更漂亮，并支持代码高亮等功能
13. 全面集成redis缓存系统，提升系统速度
14. i18n国际化

在持续改进过程中，不断的总结学习django框架，QuerySet的熟练使用，模板，全局处理器，静态资源等。
后面还会引入缓存redis，因为点击率这些非常易变的应该要使用缓存。目前是直接存储数据库，速度有点慢。
总之，在实际开发过程中不断的总结才是最好的学习方法。

一个人毕竟精力有限，期待在GitHub上面找到合作者共同完善这个系统。可以fork这个工程然后提交Pull Requests。

------------------------------------------
## 演示地址(用户名/密码：admin/admin)
https://yidaoblog.herokuapp.com/
------------------------------------------

首页效果：
![最新效果图1](http://yidaospace.qiniudn.com/simple001.jpg "最新效果图1")

顶踩功能展示：
![最新效果图2](http://yidaospace.qiniudn.com/simple002.jpg "最新效果图2")

分页效果：
![最新效果图3](http://yidaospace.qiniudn.com/simple003.jpg "最新效果图3")

富文本编辑器：
![最新效果图4](http://yidaospace.qiniudn.com/simple004.jpg "最新效果图4")

-----------------------------------------------------
## How to Contribute

You are welcome to contribute to mango-test as follow

* add/edit wiki
* report/fix issue
* code review
* commit new feature
* add testcase

Meanwhile you'd better follow the rules below

* It's *NOT* recommended to submit a pull request directly to `master` branch. `develop` branch is more appropriate
* Follow common Java coding conventions
* Put all Java class files under *com.netease* package
* Add the following [license](#license) in each Java class file

## License

(The Apache License)

Copyright (c) 2013-2014 [WinHong, Inc.](http://www.winhong.com/) and other contributors

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)