##	oasys(OA自动化办公系统)
 办公自动化（OA）是面向组织的日常运作和管理，员工及管理者使用频率最高的应用系统，极大提高公司的办公效率。

---
### 最近做了一个微信小程序 —— 垃圾识别精灵
#### 大家感兴趣的话 可以微信扫码体验一下,也可以在微信当中搜索小程序：垃圾识别精灵。 
#### ~~后面我会把相关功能再完善完善，大概在 8月底到9月初 会开源出来的。 敬请期待哟~~。
#### 现已开源，去看看吧.可以加我微信好友一起交流——>  https://gitee.com/aaluoxiang/GarbageSort
 
 

 

  -->

| 首页 | 分类页 | 分类详情 | 搜索页 |
| :--------: | :--------:| :--: |:--:|
|  | | | |


| 语音识别 | 挑战赛 | 挑战赛等级 | 挑战赛详情 |
| :--------: | :--------:| :--: |:--:|
|  | | | |

 | -->
 | | -->

---

###	1.项目介绍
oasys是一个OA办公自动化系统，使用Maven进行项目管理，基于springboot框架开发的项目，mysql底层数据库，前端采用freemarker模板引擎，Bootstrap作为前端UI框架，集成了jpa、mybatis等框架。作为初学springboot的同学是一个很不错的项目，如果想在此基础上面进行OA的增强，也是一个不错的方案。
### 2.框架介绍
#### 项目结构
![项目结构](https://images.gitee.com/uploads/images/2018/0926/164310_e781580c_1277461.png "项目结构目录.png")
#### 前端

| 技术      |    名称| 版本|	官网|
| :--------: | :--------:| :--: |:--:|
| freemarker|模板引擎|springboot1.5.6.RELEASE集成版本|https://freemarker.apache.org/|
| Bootstrap|前端UI框架|3.3.7|http://www.bootcss.com/|
| Jquery|快速的JavaScript框架|1.11.3|https://jquery.com/|
|kindeditor|HTML可视化编辑器|4.1.10|http://kindeditor.net|
|My97 DatePicker|时间选择器|4.8 Beta4|http://www.my97.net/|

#### 后端

| 技术 | 名称 | 版本 | 官网 |
| :--------: | :--------:|:---:|:------:|
|SpringBoot|SpringBoot框架|1.5.6.RELEASE|https://spring.io/projects/spring-boot|
|JPA|spring-data-jpa|1.5.6.RELEASE|https://projects.spring.io/spring-data-jpa|
|Mybatis|Mybatis框架|1.3.0|http://www.mybatis.org/mybatis-3|
|fastjson|json解析包|1.2.36|https://github.com/alibaba/fastjson|
|pagehelper|Mybatis分页插件|1.0.0|https://pagehelper.github.io|

### 3.部署流程

	    1.下载项目、把oasys.sql(原tr18lx.sql)导入本地数据库
		2. 修改application.properties，
		3. 修改数据源，oasys——>自己本地的库名，用户名和密码修改成自己的
		4. 修改相关路径，配置图片路径、文件路径、附件路径
		5. OasysApplication.java中的main方法运行，控制台没有报错信息，数据启动时间多久即运行成功
		6. 在浏览器中输入localhost:8088/logins
		
### 4. 演示地址

#####     演示地址链接：http://oa.lxsir.cn:8088/index (维护中，暂时将关闭)
#####     账号：test      密码：test
#####     账号：soli      密码：123456

 

如果对项目感兴趣，请Watch、Star项目

 


###  6.项目截图

![演示1.gif](https://images.gitee.com/uploads/images/2019/0927/141250_aeec4d38_1277461.gif)
![演示4.gif](https://i.loli.net/2018/09/26/5bab4565b121e.gif)
![演示3.gif](https://images.gitee.com/uploads/images/2019/0927/141251_4ef0327c_1277461.gif)

![主页面.png](https://images.gitee.com/uploads/images/2019/0927/141250_2286d104_1277461.png)
![登陆页面.png](https://images.gitee.com/uploads/images/2019/0927/141250_f5277aa8_1277461.png)
![文件管理.png](https://images.gitee.com/uploads/images/2019/0927/141250_491ce25d_1277461.png)
![讨论区.png](https://images.gitee.com/uploads/images/2019/0927/141251_d4992cd4_1277461.png)
![新建流程.png](https://images.gitee.com/uploads/images/2019/0927/141251_c7d89853_1277461.png)
![通讯录.png](https://images.gitee.com/uploads/images/2019/0927/141251_bcf9cbda_1277461.png)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)