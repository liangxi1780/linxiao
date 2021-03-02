#[线上访问地址](http://www.xuguobin.club/projects/elm/index.html)

注意：

 * 我的服务器内存有限，反应时间可能有些延迟。
 * 请不要往我服务器内插入恶意代码。
 * 不要往我服务器传送过多的数据。
 * 用户名：admin；密码：1111

-------

###技术栈

 * 前端部分
	vuejs，vuex，axios，element-ui，webpack
 * 后台部分
	koa2，mysql

###安装和运行

 * 后台部分
	安装依赖
	```npm install``` 
	```node index``` 
	成功执行！

 * 前端部分
	安装依赖
	```npm install``` 
	```npm run dev``` 
	成功执行！

写的不好，欢迎star和fork。

###项目更新

 * 第二次更新（2018 4月21日）
		将axios操作抽离成单独的app.js文件
 * 第三次更新（2018 4月21日）
 		提交了后台代码

###项目结构

 

├── README.md           
├── build              // 构建服务和webpack配置
├── config             // 项目不同环境的配置
├── index.html         // 项目入口文件
├── package.json       // 项目配置文件
│
├── server             // 项目后台
│   ├── api            // api操作
│   ├── db             // 与数据库交互
│   ├── index.js       // 后台入口文件
│   └── package.json   // 项目配置文件
│
├── src                // 生产目录
│   ├── api            // axios操作
│   ├── components     // 组件
│   ├── router         // 路由
│   ├── store          // vuex状态管理器
│   ├── App.vue        // 首页
│   └── main.js        // Webpack 预编译入口
│     

 


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)