##  avue1.0发布了！！！欢迎点击演示地址体验 
简体中文
欢迎加入QQ交流群，互相学习  
一键加群：    

演示地址:[http://122.4.205.228:7777](http://122.4.205.228:7777) 

码云地址:[https://gitee.com/smallweigit/avue](https://gitee.com/smallweigit/avue) 

github地址：[https://github.com/nmxiaowei/avue](https://github.com/nmxiaowei/avue) 

## 简介

`avue` 是一个后台集成解决方案支持SSR(服务端渲染)和SPA(单例页面),它基于 [Vue.js](https://github.com/vuejs/vue) 和 [element](https://github.com/ElemeFE/element)。它使用了最新的前端技术栈，权限验证，第三方网站嵌套等功能，很多功能还在开发，敬请期待  
`1.vuex本地持久化存储,封装h5的sessionStorage和localStorage`  
`2.加入了本地离线的包引入方法去引入vue，vue-router等第三方包` [详细介绍](https://my.oschina.net/sunshineS/blog/1583563)  
`3.支持SSR服务端渲染(express)`[vue-server-renderer](https://ssr.vuejs.org/zh/)  
`4.支持阿里巴巴图标库在线调用，自动同步图标` [阿里巴巴图标库](http://www.iconfont.cn/)  
`5.支持iframe嵌套第三方网站`[详细介绍](https://my.oschina.net/sunshineS/blog/1615716)  
`6.支持js动态可配CRUD和FORM,节约大量开发成本，配置字典接口自动匹配字典`  
`7.支持多种登录方式,本地验证码校验和服务端验证码校验`  
`8.全局错误日志记录`  
`9.scss模块化开发`  
`10.增加系统管理模板(用户管理,角色管理,菜单管理——基于本框架的crud组件自动生成)`  
`11.打包后docker一键部署脚本基于nginx镜像（具体的可以修改./src/docker/Dockerfile）`


**支持路由改变单例页面title**
 
   
 

**权限动态切换**
 
   
 

**实例**
 
   
 


**登录**
 
   
 

**权限测试页面**
 
   
 

**错误页面**
 
   
 

**错误日志记录**
 
   
 

**CRUD**
 
   
   
 

**FORM**
 
   
 

**用户管理**
 
   
 

**角色管理**
 
   
 

**菜单设置**
 
   
 

**阿里巴巴图标库(在线调用)**
 
   
 

**登录页面SSR渲染**
 
   
 

**主页**
 
   
 

**第三方网站**
 
   
 

## 功能
```
- 全局错误日志记录
- vuex持久化存储
- 锁屏
- SSR渲染页面
- 登录/注销
 - 用户名登录
 - 验证码登录
 - 第三方登录(开发中)
- 权限验证
- 第三方网站嵌套
- CRUD(增删改查)
- FORM(动态生成)
- 阿里巴巴图标库(在线调用)
- 系统管理
 - 用户管理
 - 角色管理
 - 菜单管理
- 更多功能开在开发
```

### 按钮的显隐控制
返回的vuex对象中额permission数组包括按钮的权限 例如: ['sys_crud_add', 'sys_crud_export'], crud的增加按钮和导出按钮

### 全局错误日志记录
放开./src/page/errlog/index.vue中的errorA的组件即可测试他是存储在本地，可以自己回掉方法上传服务器，调用CLEAR_ALL_ERR方法清空本地

### vuex持久化存demo请看
详细demo请看./src/store/modules/tgs.js实例
```bash
...
state:{
  ...
  tag: getStore({ name: 'tag' }) || tagObj
},
...
 mutations: {
  ...
  setStore({ name: 'tagList', content: state.tagList, type: 'session' })
  ...
 }
```
### 数据加密工具类——在./src/util/util.js中encryption
支持Base64和Aes加密
```bash
const data ={
  username:'admin',
  password:'123456'
}
const userInfo = encryption({
    data: data,//加密的数据
    key:'123',//aes加密时的类型，不是aes加密不用传
    type: 'Base64',//要加密的类型 Base64 || Aes
    param: ['useranme', 'password'] //要加密的字段
});
```
### CRUD和FORM使用说明————根据配置json文件自动生成CRUD和FORM，并且配置字典接口，自动匹配字典
详细demo请看./src/page/table/index.vue和./src/page/form/index.vue实例实例
```bash
子定义操作按钮 
 
     权限 
 
js自动配置crud 
{
  border: true,//表格是否显示边框
  index: true,///表格是否显示序号
  selection: true,//表格是否显示可选select
  dic:['GRADE','SEX'],//传入需要获取字典的变量，看vuex中的getDic方法
  column: [
    {
      label: "用户名",//表格的标题
      prop: "username",//表格的key
      width: "150",//表格的宽度
      fixed: true,//是否冻结列
      hide:true,//是否隐藏
      span:12,//表单格栅显示的列
      type:'select', //select | radio | checkbox | date 默认为text
      visdiplay:true,//表单不显示
      overHidden: true,//超出省略号显示
      dicData: 'GRADE', //传入需要引用的字典
      ],//type的数据字典,当type为：select | radio | checkbox 加载
      dataDetail: val => {
        return ` ${val} `;;//是否对列表数据处理
      },
      rules: [{ required: true, message: "请输入用户名", trigger: "blur" }] //表单校验规则
    }
}
```

## 开发
```bash
# 克隆项目
git clone https://gitee.com/smallweigit/avue.git

# 安装依赖
npm install
   
# 建议不要用cnpm安装 会有各种诡异的bug 可以通过如下操作解决 npm 下载速度慢的问题
npm install --registry=https://registry.npm.taobao.org

# 启动服务
npm run dev
```

## 调试与发布
```bash
# 构建测试环境
npm run dev

# 构建生成环境
npm run build

# 构建SSR渲染页面
npm run start

```


## 其它
```bash
# 代码检测
npm run lint

# 单元测试
npm run karma

# 构建SSR客户端代码
npm run build:client

# 构建SSR服务端端代码
npm run build:server
```



## License

[MIT](https://gitee.com/smallweigit/avue/blob/master/LICENSE)

Copyright (c) 2017-present Smallwei QQ:1634566606


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)