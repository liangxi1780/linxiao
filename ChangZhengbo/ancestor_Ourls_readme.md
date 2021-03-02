# Ourls

Ourls是一个基于发号和hashid的短网址服务，灵感来源于知乎上关于短址算法的一个讨论——
[http://www.zhihu.com/question/29270034](http://www.zhihu.com/question/29270034)。

## 特征/Feature

Ourls会根据sha1值来判断原url在数据库中是否已存在，若不存在则新增记录后对记录id进行hash，产生短网址。

Ourls会对输入的url进行标准化处理，若为缺少scheme的url，会默认自动加上`http://`，
并且会对url的query参数进行排序和urlencode等。

## 演示/Demo

[在线演示/Online Demo](http://skyx.in)

## 安装/Install

下载源码后运行`composer install`安装依赖包，或者运行`composer create-project takashiki/ourls`。

然后将urls.sql导入数据库中，将app目录下config.sample.php重命名为config.php并按自己实际情况修改相关配置项。

> git clone and composer install or composer create-project takashiki/ourls

> import urls.sql to your database

> rename app/config.sample.php to app/config.php 

> modify the config file according to your situation

### License

Ourls is open-sourced software licensed under the 
[MIT license](http://opensource.org/licenses/MIT)

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)