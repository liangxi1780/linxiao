## zrlog 使用 JFinal 构建的个人博客程序
> blog 虽然慢慢的消失, 但是总有不愿意去用QQ空间,微博,微信等,而是希望有个自己的个人主页,于是就有这个博客程序

### 部署环境前提
* 1.jre 版本 >= 1.6
* 2.tomcat 版本 >=6，jetty > 6
* 3.mysql

### 功能
* 1.实现了的日志，分类，评论，的管理
* 2.支持插件模式 [如何编写一个zrlog插件 http://blog.94fzb.com/post/175](http://blog.94fzb.com/post/175) 
* 3.后台动态变更前台主题
* 4.支持第三方评论插件
* 5.提供 editormd 个主流的富文本编辑器，基本上满足了管理员的编辑
* 6.使用ecache缓存公共数据,访问速度更快
* 7.支持页面静态化
* 8.支持扩展第三方云存储（默认七牛）
* 9.支持数据库定时备份

### 系统安装
* 1.下载 [最新 war](http://dl.94fzb.com/release/zrlog.war) 放在tomcat的webapps
* 2.访问 http://host:port/zrlog/install
* 3.填写数据，管理员信息，完成安装
* 4.[程序演示地址 http://blog.oschina.mopaas.com](http://blog.oschina.mopaas.com/)

### 联系方式
* QQ 交流 504008147
* 邮件 xchun90@163.com
* 程序问题反馈  http://blog.94fzb.com/post/feedback

### Changelog

#### 1.4 (2015-06-05)
* 优化后台部分逻辑
* 加入邮件服务
* 移出kindeditor相关文件

#### 1.4.2 (2015-09-20)
* 加入新的评论邮件通知选项
* 多说绑定页面，不用手动输入
* IP 黑名单
* 文件 html,css,js 支持在线编辑


### 一些截图
![编辑页面](http://fz-blog.qiniudn.com/attached/image/20150328/20150328221806_648.jpg "编辑页面")

![文章管理](http://fz-blog.qiniudn.com/attached/image/20150328/20150328222511_459.jpg)

![模板管理](http://fz-blog.qiniudn.com/attached/image/20150328/20150328222526_340.jpg)

![插件中心](http://fz-blogjfinal.qiniudn.com/attached/image/20150328/20150328222541_30.jpg)

![变更文章页面](http://fz-blog.qiniudn.com/attached/image/20150328/20150328222557_275.jpg)

![前台页面](http://fz-blog.qiniudn.com/attached/image/20150328/20150328222609_521.jpg)

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)