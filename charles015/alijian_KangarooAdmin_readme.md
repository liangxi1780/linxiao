###  **KangarooAdmin** 
在线体验：[http://kangarooadmin.duapp.com](http://kangarooadmin.duapp.com/login/index.html) 
账号密码: admin/123456
```
### 分支说明
```
1. v_1.0:启航版:[https://git.oschina.net/zhougaojun/KangarooAdmin/tree/v_1.0/](https://git.oschina.net/zhougaojun/KangarooAdmin/tree/v_1.0/)
2. v_2.0:进取版:[https://git.oschina.net/zhougaojun/KangarooAdmin/tree/v_2.0/](https://git.oschina.net/zhougaojun/KangarooAdmin/tree/v_2.0/)
3. master:不断增强完善版本。

```
### 项目说明
```
1.KangarooAdmin是以SpringMVC+Mybatis+MySQL为核心开发的精简后台基础系统。
2.包含用户管理,角色管理,部门管理,权限管理,菜单管理,日志管理等常用业务模块。
3.使用AdminLTE作为前端UI框架。
4.第三方Mybatis-plus作为ORM框架。
5.使用Kisso单点登录。
6.Encache权限缓存。
7.FreeMarker模板,页面拆分,封装公共部分。
```
### 快速开始
```
1.创建数据库KangarooAdmin,导入resource/sql/kangarooadmin.sql数据库脚本。
2.把项目导入到Eclipse中启动,端口为8080,上下文为/。
3.修改本地host加入如下一行:127.0.0.1 kangaroo.com，需另起一行。
4.地址栏输入 http://kangaroo.com:8080/login/index.html 访问，账号admin/密码123456。
5.注意域名和端口可随意定义，但一定记得修改properties/sso.properties配置文件中的sso.cookie.domain和sso.login.url,这两个配置要和自己定义的一致即可 。
![输入图片说明](http://git.oschina.net/uploads/images/2017/0112/212538_5d2a3805_89451.png "在这里输入图片标题")
![输入图片说明](http://git.oschina.net/uploads/images/2017/0112/212737_5fdcad1c_89451.png "在这里输入图片标题")
![输入图片说明](http://git.oschina.net/uploads/images/2017/0112/212936_75c22591_89451.png "在这里输入图片标题")
```
### 数据库监控
```
访问地址:http://kangaroo.com:8081/druid/sql.html,账号/密码:admin/admin,配置在web.xml中。
![输入图片说明](http://git.oschina.net/uploads/images/2017/0113/101521_312c0eae_89451.png "在这里输入图片标题")

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)