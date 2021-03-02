﻿
 

      
      
      
一个基于 Vue.js 的后台管理系统项目，目前是1.0版本，主要是权限管理系统，以后会增加更多功能，持续开发中...。


这里仅仅是vue项目，api接口工程，请查看 [Blog.Core](https://github.com/anjoy8/Blog.Core)




## 给个星星! ⭐️
如果你喜欢这个项目或者它帮助你, 请给 Star~（辛苦星咯）

*********************************************************
### 项目下载后，首先安装依赖包
```
npm install
```

### 安装成功后，运行即可
```
npm run serve // 请不要把 再一直用 dev 命令了
```
然后你就可以直接访问 http://localhost:6688


## Tips：



```
如果你想换一个端口，可以直接修改根目录下的 vue.config.js 文件

  devServer: {
    port: 2364, // 当前 admin 项目的端口号
    https: false,

而且也要代理下后端的接口地址，如果你使用 proxy 来实现跨域的话（如果用 CORS 跨域，这里就不用配置了）：

    proxy: {
      // 配置多个代理
      "/api": {
        target: "http://localhost:8081",//这里改成你自己的后端api端口地址，记得每次修改，都需要重新build

```

### 如果要部署，先执行bulid
```
npm run build
```




*****************************************************
### 三大平台同步直播

博客园：https://www.cnblogs.com/laozhang-is-phi/p/10236645.html

简  书：https://www.jianshu.com/notebooks/28621653

 CSDN：https://blog.csdn.net/baidu_35726140


 
 目录 



 
  一 || 权限后台1.0正式上线  
  二 || 完美实现 JWT 滑动授权刷新  
  三 || 动态路由配置 &amp; 项目快速开发  
  四 || NetCore + SignalR 实现日志消息推送  
        五 ║ 实现『按钮』级别权限配置  
 


 


 
******************************

## 安装

```
 git clone https://github.com/anjoy8/Blog.Admin.git
```
安装包依赖
```
npm install
```

## 运行
运行开发环境
```js
npm run serve
```

**本地访问http://localhost:2364**
```
可以在根目录的 vue.config.js 中修改端口：

  "devServer": {
     "host": "127.0.0.1",
     "port": "2364"//端口号
  },
  
  
```


## 编译
build for production and launch server
```js
npm run build
```










 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)