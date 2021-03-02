## XMall-Front
### 基于Vue开发的XMall商城前台页面
### [宣传视频](https://www.bilibili.com/video/av23121122/)
- 作者亲自制作 [点我观看](https://www.bilibili.com/video/av23121122/)
### 项目已部署，在线Demo
- 前台商城：http://xmall.exrick.cn/
- 后台管理系统：http://xmadmin.exrick.cn/
### 感谢 [yucccc](https://github.com/yucccc) 的开源 [vue-mall](https://github.com/yucccc/vue-mall) 项目提供前端页面及框架支持
### 后端全部重新开发接口，实现后台系统管理，后端接口项目请跳转至 [xmall](https://github.com/Exrick/xmall) 项目仓库查看
### 新增与优化
- [x] 优化页脚、增加商品搜索框组件
- [x] 优化登录注册界面
- [x] 新增搜索页面，实现高亮分页搜索
- [x] 新增捐赠页面，捐赠列表显示
- [x] 全部商品页面实现分页
- [x] 优化订单详情，实现查看订单进度，可对订单进行处理
- [x] 实现生成订单接口、优化地址管理编辑选择
- [x] 实现查看个人订单分页
- [x] 接入[XPay个人收款支付系统](https://github.com/Exrick/xpay)
- [x] 首页升级！重构首页，后台可配置，包括3D轮播图
- [x] 新增分类查看品牌周边等
    
![](http://oweupqzdv.bkt.clouddn.com/QQ%E6%88%AA%E5%9B%BE20171022183906.jpg "首页")

![](http://oweupqzdv.bkt.clouddn.com/QQ%E6%88%AA%E5%9B%BE20171022222841.jpg "页脚")

![](http://oweupqzdv.bkt.clouddn.com/QQ%E6%88%AA%E5%9B%BE20171022223650.jpg "搜索框组件")

![](http://oweupqzdv.bkt.clouddn.com/QQ%E6%88%AA%E5%9B%BE20171109215656.jpg "搜索结果")

![](http://oweupqzdv.bkt.clouddn.com/QQ%E6%88%AA%E5%9B%BE20171022202842.jpg "无搜索结果")

![](http://oweupqzdv.bkt.clouddn.com/QQ%E6%88%AA%E5%9B%BE20171022223142.jpg "分页")

![](http://oweupqzdv.bkt.clouddn.com/QQ%E6%88%AA%E5%9B%BE20171022190036.jpg "订单详情")

![](http://oweupqzdv.bkt.clouddn.com/QQ%E6%88%AA%E5%9B%BE20171022190107.jpg "订单进度")

![](http://oweupqzdv.bkt.clouddn.com/QQ%E6%88%AA%E5%9B%BE20171114233321.jpg "登录界面")
    
### 所用技术

- Vue 2.x
- Vuex
- Vue Router
- [Element UI](http://element.eleme.io/#/zh-CN)
- ES6
- webpack
- axios
- Node.js
- 第三方SDK
    - [极验Test-button人机验证码](http://www.geetest.com/Test-button.html)
- 第三方插件
    - [hotjar](https://github.com/Exrick/xmall/blob/master/study/hotjar.md)：一体化分析和反馈
    - [搜狐畅言评论插件](http://changyan.kuaizhan.com/)

### 本地开发运行
- 启动后端 [xmall](https://github.com/Exrick/xmall) 项目后，在 `config/index.js` 中修改你的后端接口地址配置
- 在 `src/api/goods.js` 中的 `getQuickSearch` 方法里修改你的Elasticseach服务器IP以及RESTful快速搜索提示接口配置
- `index.html` 中复制粘贴替换你的 [hotjar](https://github.com/Exrick/xmall/blob/master/study/hotjar.md) 代码
- 若不启动后端项目，勉强预览运行此前端项目可尝试注释掉 `src/main.js` 中第 `8、10、37-59` 行代码
- 在项目根文件夹下先后执行命令 `npm install` 、 `npm run dev`
- 商城前台端口默认9999 http://localhost:9999
## 部署
- 先后执行命令 `npm install` 、 `npm run build` 将打包生成的 `dist` 静态文件放置服务器中，并配置路由代理
### 技术疑问交流
- 给作者项目Star或捐赠后可加入交流群 `475743731`，还可免费获取 [慕课网学习资源](https://coding.imooc.com/class/203.html) 和 [UI框架](https://github.com/Exrick/xmall/blob/master/study/FlatLab.md) [![](http://pub.idqqimg.com/wpa/images/group.png)](http://shang.qq.com/wpa/qunwpa?idkey=7b60cec12ba93ebed7568b0a63f22e6e034c0d1df33125ac43ed753342ec6ce7)
- 个人博客：[http://blog.exrick.cn](http://blog.exrick.cn)
### 作者其他项目推荐
- 微信小程序APP 
    - 捐赠≥19.9可加群私聊群主提前下载前台源码 [预览视频](https://v.qq.com/x/page/f0627kf4x1e.html) 赠送[慕课网SpringCloud学习资源](https://coding.imooc.com/class/187.html)

    ![](http://oweupqzdv.bkt.clouddn.com/%E5%B0%8F%E7%A8%8B%E5%BA%8F%E9%A2%84%E8%A7%881.png)
- [X-Boot前后端分离开发平台](https://github.com/Exrick/x-boot)

    ![](http://oweupqzdv.bkt.clouddn.com/QQ%E6%88%AA%E5%9B%BE20180504215601.png)
### 捐赠
![](http://oweupqzdv.bkt.clouddn.com/FgwHSk1Rnd-8FKqNJhFSSdcq2QVB.png)

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)