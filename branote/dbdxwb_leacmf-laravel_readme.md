leacmf是一款基于Laravel5.5+layui开发的极速App后台开发框架。
===============

thinkphp版本进 https://github.com/lea21st/leacmf-thinkphp

## **主要特性**

* 后台RBAC权限管理系统
* 完善的前端功能组件开发
    * 基于`layui`开发
    * 封装了部分方法，开发快速简单，没有文档，看例子，如调用富文本编辑器` @include('widget.kindeditor',['field'=>'content']) ` 调用图片上传` @include('widget.upload',['field'=>'picture']) `
 * 自动高亮菜单，自动面包屑，根据权限自动生成菜单树
 * 集成api验证,开发api和后台都快速方便
  
  
  ## **安装方式**  
  
Laravel 需要 PHP &gt;= 7.1以上的版本，并且同时需要PHP安装以下扩展

```
- cURL extension

- mbstring

- BC Math
```
使用 ` git ` 将代码clone到本地，导入最新的数据库文件(迁移文件等会)，然后运行

```
composer update
```
在`.env`中配置好数据库和redis等。

顺便生成secret,`php artisan key:generate`和`php artisan jwt:secret`,

## **在线演示**
[ip/localhost]/admin/

用户名：admin
密　码：123456

## **二次开发（暂时随便写下，文档继续完善）**

 

* 更多功能暂时看源码吧，太忙，正式版未出之前不要用于正式环境，默认使用redis作为默认缓存，如未使用redis，在配置缓存中改成其它

## **界面截图**
![1](/public/11.png "1")
![2](/public/2.png "2")
![3](/public/3.png "3")
![4](/public/4.png "4")
![5](/public/4.png "5")

## **特别鸣谢**

感谢以下的项目,排名不分先后

Laravel：https://laravel.com/

layui：http://www.layui.com



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)