
  RXThinkCMF_TP5.1权限(RBAC)及内容管理框架 

 
	 
	     
	 
	 
	     
	 
	 
         
     
	 
          
     
     
          
     
 

 
 
 

### 如果对您有帮助，您可以点右上角 "Star" 支持一下 谢谢！
### 如果您想获悉项目实时更新信息，您可以点右上角      感谢您的支持！git 
### 官方网址：http://www.rxthink.cn/
### 帮助文档：http://docs.tp5.1.rxthink.cn
### 本项目还在不断开发完善中,如有建议或问题请官方论坛反馈，论坛地址:http://www.rxthink.cn

## 项目介绍
RXThinkCMF_TP5.1 基于 ThinkPHP5.1 +Layui2.4.5 开发权限(RBAC)及内容管理框架，框架中集成了权限管理、模块管理、插件管理、钩子管理、数据库管理、富文本编辑器(已集成ueditor,kindeditor)，后台支持多主题切换、布局管理、广告管理、配置管理、字典管理、切图管理、CMS内容管理等常用功能模块，以方便开发者快速构建自己的应用。RXThinkCMF_TP5.1框架专注于为中小企业提供最佳的行业基础后台框架解决方案，执行效率、扩展性、稳定性值得信赖，操作体验流畅，使用非常优化，欢迎大家使用及进行二次开发。

* 模块化：全新的架构和模块化的开发机制，便于灵活扩展和二次开发。
* 模型/栏目/分类信息体系：通过栏目和模型绑定，以及不同的模型类型，不同栏目可以实现差异化的功能，轻松实现诸如资讯、下载、讨论和图片等功能。通过分类信息和栏目绑定，可以自动建立索引表，轻松实现复杂的信息检索。
* RXThinkCMF_TP5.1是一套基于ThinkPHP + Layui开发出来的框架。
* 支持SQLServer、MySQL、Oracle、PostgreSQL、SQLite等多数据库类型。模块化设计，层次结构清晰。  
* AUTH权限认证，操作权限控制精密细致，对所有管理链接都进行权限验证，可控制到导航菜单、功能按钮。提高开发效率及质量。
* 常用类封装，日志、缓存、验证、字典、文件（本地、七牛云）。等等，目前兼容浏览器（Chrome、Firefox、360浏览器等）
* 适用范围：可以开发OA、ERP、BPM、CRM、WMS、TMS、MIS、BI、电商平台后台、物流管理系统、快递管理系统、教务管理系统等各类管理软件。
 
## 环境要求:
* PHP >= 5.6.0
* PDO PHP Extension
* MBstring PHP Extension
* CURL PHP Extension
* 开启静态重写
* 要求环境支持pathinfo
* 要求安装Zip扩展(插件/模块市场需要)


### 功能特性
- **严谨规范：** 提供一套有利于团队协作的结构设计、编码、数据等规范。
- **高效灵活：** 清晰的分层设计、钩子行为扩展机制，解耦设计更能灵活应对需求变更。
- **严谨安全：** 清晰的系统执行流程，严谨的异常检测和安全机制，详细的日志统计，为系统保驾护航。
- **组件化：** 完善的组件化设计，丰富的表单组件，让开发列表和表单更得心应手。无需前端开发，省时省力。
- **简单上手快：** 结构清晰、代码规范、在开发快速的同时还兼顾性能的极致追求。
- **自身特色：** 权限管理、组件丰富、第三方应用多、分层解耦化设计和先进的设计思想。
- **高级进阶：** 分布式、负载均衡、集群、Redis、分库分表。 
- **命令行：** 命令行功能，一键管理应用扩展。 


## 开发者信息
* 系统名称：RXThinkCMF_TP5.1专业版权限(RBAC)及内容管理框架  
* 作者[牧羊人]：南京RXThink研发工作室
* 作者QQ：1175401194  
* 官网网址：[http://www.rxthink.cn/](http://www.rxthink.cn/)  
* 文档网址：[http://docs.tp5.1.rxthink.cn](http://docs.tp5.1.rxthink.cn)  
* 开源协议：Apache 2.0

### jwt token鉴权机制
jwt token鉴权机制是指若需要请求服务器接口，必须通过AuthController获取一个请求令牌(jwt token)，持有jwt token的用户才可以访问服务器的其他资源，如果没有此令牌，则访问接口会直接忽略，请求获取jwt token时，需要携带credenceName和credenceCode(可以是账号密码，可以是手机号验证码等等)，校验credenceName和credenceCode成功后，会颁发给客户端一个jwt token还有一个随机字符串，用于传输过程中对数据进行签名用，签名机制请见下面介绍.基于token的鉴权机制类似于http协议也是无状态的，它不需要在服务端去保留用户的认证信息或者会话信息.这就意味着基于token认证机制的应用不需要去考虑用户在哪一台服务器登录了，这就为应用的扩展提供了便利.

### RXThinkCMF版本说明

| 版本名称 | 说明 | 地址 |
| :---: | :---: | :---: |
| RXThinkCMF_TP5.1专业版 | 最新开源版本，master分支 | https://gitee.com/ruoxi520_admin/RXThinkCMF_TP5.1 |
| RXThinkCMF_TP5.1旗舰版 | 最新开源版本，master分支 | https://gitee.com/ruoxi520_admin/RXThinkCMF_TP5.1_PRO |


## 后台演示（用户名:admin 密码:admin123）
- RXThinkCMF_TP5.1版本：[http://manage.tp5.1.rxthink.cn/](http://manage.tp5.1.rxthink.cn/)


## 技术支持

技术支持QQ：1175401194    
[官方交流群：262206078](http://shang.qq.com/wpa/qunwpa?idkey=84899631e9f8d6b1d4c2749dbb1ebecc3faca80b3595877a9109447941128bf1)

## QQ交流群

官方交流群：262206078 [![点击加群](https://images.gitee.com/uploads/images/2019/0519/192303_fb9f6f39_478496.png "点击加群")](https://jq.qq.com/?_wv=1027&k=5sCX1VA)，如有问题会有人解答和修复，免费开源版源码请至群内获取。


## 官方技术交流二维码：期待您的加入，欢迎您跟RXThink团队一起成长！！

![QQ群二维码](http://images.tp5.1.rxthink.cn/demo/qq_group.png)

## 效果图展示

#### 1、系统登录
 ![系统登录](http://images.tp5.1.rxthink.cn/demo/1.png)
 
#### 2、系统主页
 ![系统主页](http://images.tp5.1.rxthink.cn/demo/2.png)
 
#### 3、func.js方法类库
 ![JS核心类库](http://images.tp5.1.rxthink.cn/demo/3.png)
 
#### 4、common.js函数类库
 ![JS核心类库](http://images.tp5.1.rxthink.cn/demo/4.png)
 
#### 5、列表JS案例
 ![列表JS案例](http://images.tp5.1.rxthink.cn/demo/5.png)
 
#### 6、缓存基类封装
 ![底层缓存基类封装](http://images.tp5.1.rxthink.cn/demo/6.png)
 
#### 7、模型基类封装
 ![模型基类封装](http://images.tp5.1.rxthink.cn/demo/7.png)
 
#### 8、系统公共函数封装
 ![系系统公共函数封装](http://images.tp5.1.rxthink.cn/demo/8.png)

## 部署说明

[点击查看技术文档](http://docs.tp5.1.rxthink.cn)


## 更新说明

# 2020-01-16更新  
1、【完成】新增阿里短信发送工具包 ；
2、【完成】新增封装极光推送、友盟推送工具类；


# 2020-01-03更新  
1、【完成】新增网站配置管理；


# 2020-01-02更新  
1、【完成】新增中间件的功能；
2、【完成】修正系统已收集的BUG；


# 2020-01-01更新  
1、【完成】系统架构进行重新设计，全部采用环境变量的形式进行参数配置，移除config.inc.php配置文件(多数人不理解此文件) ；
2、【完成】动态设置数据表前缀，安装时可以自定义数据表前缀，而不是之前指定的前缀think_；


# 2019-12-25更新  
1、【修复】解决新版权限按钮小组件失效的问题  
2、【修复】修复在使用中已完善的BUG


# 2019-05-17更新  
1、【新增】按钮组件公共JS方法实现btnFunc  
2、【新增】table数据列表新增【一键复制】、【重置缓存】的节点组件


# 2019-05-12更新  
1、【新增】上传图片JS组件UploadFile的实现，switch开关组件formSwitch组件的实现   
2、【新增】数据库管理模块，实现了立即备份、优化表、回复表、数据库还原等  


# 2019-05-05更新  
1、【新增】查询、导出Excel、导入Excel、批量启用、批量禁用等功能按钮组件化   
2、【完成】附件管理的功能     
3、【完成】系统配置管理   
4、【优化】框架核心JS模块的优化，实现JS、CSS、图片等Webpack一键打包的功能   

  
# 2019-05-02更新  
1、【新增】增加提交、重置、关闭按钮的组件灵活配置功能（submit|立即提交,reset|重置,close|关闭）  
2、【完成】Checkbox常规选择框、复杂选择框的组件实现  
3、【完成】Radio单选框的组件化实现  
4、【新增】CURD（增删改查）权限验证模块  
5、【新增】Redis缓存优化


# 2019-04-20更新  
1、【新增】字典类型模块   
2、【新增】字典管理模块的实现    
3、【新增】配置分组模块    
4、【新增】配置模块的整理功能优化，系统相关配置的表单式管理  
5、【完成】城市选择组件的常规组件和复杂组件的完善   


# 2019-04-05更新
1、【优化】优化系统底层缓存存储  
2、【新增】新增BaseModel类的常用CURD（增删改查）常规方法及业务方法    
3、【新增】缓存调用方法setCache、getCache、resetCache、deleteCache方法的底层优化  


# 2019-03-15更新
1、【完善】新增图片处理常用函数：save_image（保存图片）、create_image_path（创建系统图片存储路径）、save_remote_image（保存网络图片到本地）  
2、【新增】基类验证类的实现：BaseValidate（验证规则、验证描述、验证场景）    
3、【新增】新增模型常用函数：getCount、getSum、getMax、getMin、getAvg、getValue、getOne、getRow、getColumn、getList等  
  
 
# 2019-03-05更新
1、【完成】对底层架构做了调整，实现了模板继承调用及Layout模板布局  
2、【新增】模块列表面包屑    
3、【新增】错误提示403、404、500页面  


# 2019-02-10更新
1、【新增】系统应用初始化行为InitApp  
2、【新增】初始化基础配置行为InitBase    
3、【新增】注册钩子InitHook  


# 2019-01-27更新
1、【新增】撰写系统常用函数文件common.php  
2、【新增】自定义系统常用函数类function.php文件，备注：function.php文件是系统为了扩展，对开发者自行定义函数的文件，二次开发自定义函数全部写于此，禁止在系统框架common.php文件中进行书写，以免影响系统后续升级优化   
3、【完善】调整及优化系统控制器基类配置CommonBase.php文件  
4、【新增】数据库常用操作方法get_tables_list、table_exist、drop_table、get_table_fields、field_exist等底层函数  
5、【新增】CRUD扩展方法doInsert、doUpdate、doDelete、doMark（软删除方法）  


# 2018-12-15更新  
1、为了框架能够更好的发展，年底对框架从底层架构进行重构，新增了扩展及行为钩子、插件、组件，使得系统能更加灵活、更加友好；通过组件化、插件化的目的在于提供系统的可维护性、可操作性及提高研发效率，使得在开发过程中可以简单的通过配置、权限赋予、模块调用等实现模块化的开发  
2、目前系统架构依然采用传统的MVC架构模式，主要是为了广大的用户考虑，目前大部分人对MVC的架构模式比较熟悉和熟练的使用，后期如果有需要，我们会重构系统实现MVP、MVVM或者其他主流架构模式  
3、新重构的系统版本定位：V2.0  


# 2018-11-01更新
1、【新增】岗位模块、职级模块  
2、【新增】友情链接模块、城市模块  
3、【新增】站点模块、栏目模块  
4、【新增】布局描述模块、布局模块  
5、【新增】广告描述模块、广告模块  


# 2018-09-18更新
1、【完善】重点优化系统架构部分，实现CRUD权限管理基础性架构设计及研发，方便权限灵活配置  
2、【新增】新增人员模块功能的实现  
3、【新增】组件底层架构的搭建及一些常用基础组件的研发，如：switch_check（开发组件）、radio_check（单选组件）、single_select（常规选择下拉组件）等  


# 2018-07-08更新
1、【准备】设计系统框架架构，目前框架支持大后台、API接口、前台、WAP站、Script脚本等  
2、【准备】准备框架所需要的第三方组件及文件（支持Composer）  
3、【准备】重点选定系统框架采用传统的MVC架构模式  
4、【准备】研发框架基础RBAC权限管理模块的搭建及基础模块的开发  


# 2018-03-08更新
1、【准备】整体框架结构的规划、设计、排期与实施  
2、【优化】鉴于RXThinkCMF_TP5.1_TP3.2_V2.0框架的设计和实践，对框架整体性做重构与改进  

## 安全&缺陷
如果你发现了一个安全漏洞或缺陷，请发送邮件到 1175401194@qq.com,所有的安全漏洞都将及时得到解决。


## 鸣谢
感谢[ThinkPHP](http://www.thinkphp.cn)、[JQuery](http://jquery.com)、[Layui](http://www.layui.com)等优秀开源项目。

## 版权信息

RXThinkCMF_TP5.1提供个人非商业用途免费使用，商业需授权。

本项目包含的第三方源码和二进制文件之版权信息另行标注。

版权所有Copyright © 2017-2019 rxthink.cn (http://www.rxthink.cn)

All rights reserved。

更多细节参阅 [LICENSE.txt](LICENSE.txt)

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)