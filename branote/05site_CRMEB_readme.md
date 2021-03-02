#### 说明书

###### 感谢

> 感谢 众邦科技，因为你们的努力才有了这个软件的存在, 感谢 感谢 感谢

###### 运行环境 PHP 5.6.40

###### NGINX 配置

```text
server {
    listen       80;
    server_name  www.wx.x.com;

    root /var/www/html/CRMEB/public;
    index index.html index.htm index.php;

    location / {
        #try_files $uri $uri/ /index.php?$query_string;
        if (!-e $request_filename ) {
            rewrite ^/(.*)$ /index.php?s=$1 last;
        }
    }

    error_page   500 502 503 504  /50x.html;
    location = /50x.html {
        root /var/www/html;
    }

    location ~ \.php$ {
        fastcgi_pass   127.0.0.1:9000;
        fastcgi_index  index.php;
        fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
        include        fastcgi_params;
    }
}
```

  CRMEB客户管理+电商管理系统  
 
     
         
     
 
         
     
     
         
     
      
         
     
 

### 本项目持续维护,如有建议或问题请[在这里提出](https://gitee.com/ZhongBangKeJi/CRMEB_WeChatMiniProgram/issues)

### 如果对您有帮助，您可以点右上角 "Star" 支持一下 谢谢！
### 公众号和小程序打通版 https://gitee.com/ZhongBangKeJi/CRMEB
### 帮助文档：https://www.kancloud.cn/crmeb/crmeb/662420
### 如有建议或问题请官方论坛反馈，论坛地址:http://bbs.crmeb.net
## CRMEB推荐服务器配置
入门级配置
```
CPU：1核
内存：1G
实例规格：突发性能t5实例
带宽：1M
系统：CentOS 7.4 64位(推荐)
价格：366元/年 933.3 元/三年
```
 查看服务器详情 

标准级配置
```
CPU：2核
内存：4G
实例规格：突发性能t5实例
带宽：2M
系统：CentOS 7.4 64位(推荐)
价格：936元/年 2386.8 元/三年
```
 查看服务器详情 

##  :couple_with_heart: 小程序页面展示
 
 
   
   
   
 
 
   
   
   
 
 
   
   
   
 
 

##   :tw-1f340: 演示地址:tw-1f340:
   演示站后台:[  crmeb_v2.5  ]       
 http://demo25.crmeb.net 
   账号：demo
   密码：crmeb.com

![输入图片说明](https://images.gitee.com/uploads/images/2019/0302/165543_801cf1e6_892944.jpeg "二维码.jpg")

# :tw-1f1ef-1f1f5: 付费版 :tw-1f1ef-1f1f5:   详情  :tw-1f680:  [  进入淘宝  ]
[![输入图片说明](https://images.gitee.com/uploads/images/2019/0122/114739_a48f5bfd_892944.gif "taobao(1).gif")](https://s.click.taobao.com/W7hVkLw)

```
淘宝超值版:

CRMEB微信公众号v2.6版：除了以上功能还带砍价、拼团功能

CRMEB微信小程序v2.6版：除了以上功能还带砍价、拼团功能

CRMEB微信公众号小程序打通v2.6版：除了以上功能还带砍价、拼团功能 需要申请微信开放平台

还有定制开发服务，例如：预约系统、O2O、付费阅读、多店版、多商家版

官网线下定制服务版：http://www.crmeb.com
```


##  :tw-1f1fe:  用法

   下载: 

```
Git clone https://gitee.com/ZhongBangKeJi/CRMEB_WeChatMiniProgram.git
```
    文档地址:https://gitee.com/ZhongBangKeJi/CRMEB_WeChatMiniProgram/wikis


##  :tw-1f1f2: 目录结构

目录结构[查看](https://gitee.com/ZhongBangKeJi/CRMEB/wikis/pages/preview?title=%E7%A8%8B%E5%BA%8F%E7%9B%AE%E5%BD%95&parent=)：


##  :tw-1f1f6: 问题反馈

在使用中有任何问题，请使用以下联系方式联系我们

### :tw-1f427: QQ交流群
 CRMEB微信开发6群: 341864990    
|CRMEB微信开发3群:69741389   

Gitee: https://gitee.com/ZhongBangKeJi/CRMEB_WeChatMiniProgram/issues

## 定制开发
定制开发单商户商城分销系统、多商家商城分销系统、多店商城系统、预约系统、付费阅读系统、外卖系统等。梦想的路上我们与您同行！
联系QQ：98718401
联系电话：400-8888-794

##  系统组件开源项目

#### form-builder

tp5 PHP表单生成器，快速生成现代化的form表单。包含复选框、单选框、输入框、下拉选择框等元素以及,省市区三级联动,时间选择,日期选择,颜色选择,文件/图片上传等功能。
form-builder : https://github.com/xaboy/form-builder

##  :tw-1f1f9: 特别鸣谢
感谢以下的项目,排名不分先后

ThinkPHP：http://www.thinkphp.cn

Bootstrap：http://getbootstrap.com

jQuery：http://jquery.com

iView：https://www.iviewui.com

Vue：https://cn.vuejs.org/

font-awesome： https://fontawesome.com/?from=io

umeditor：http://ueditor.baidu.com/website/umeditor.html


版权信息
CRMEB v2.5.* 遵循GPL3.0开源协议发布，并提供免费使用。

本项目包含的第三方源码和二进制文件之版权信息另行标注。

版权所有Copyright © 2017-2018 by CRMEB (http://www.crmeb.com)

All rights reserved。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)