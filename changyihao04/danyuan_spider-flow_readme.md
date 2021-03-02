# spider-flow

#### 介绍
新一代爬虫平台，以图形化方式定义爬虫流程，不写代码即可完成爬虫。
>  **QQ交流群：720832964** 

#### 使用说明
[点击跳转](https://www.spiderflow.org)


#### 演示站点
[点击跳转](http://demo.spiderflow.org/)
> 服务器配置较低,如有卡顿请谅解

### 项目结构
```
spider-flow
├── spider-flow-api -- 插件开发的依赖
├── spider-flow-core -- 核心包
├── spider-flow-web -- web界面
```

#### 特性
- [x] 支持css选择器、正则提取
- [x] 支持JSON/XML格式
- [x] 支持Xpath/JsonPath提取
- [x] 支持多数据源、SQL select/insert/update/delete
- [x] 支持爬取JS动态渲染的页面
- [x] 支持代理
- [x] 支持二进制格式
- [x] 支持保存/读取文件(csv、xls、jpg等)
- [x] 常用字符串、日期、文件、加解密等函数
- [x] 支持流程嵌套
- [x] 支持插件扩展(自定义执行器，自定义函数）
- [ ] 任务监控
- [x] 支持HTTP接口

#### 插件列表
- [x] [Selenium插件](https://gitee.com/jmxd/spider-flow-selenium)
- [x] [Redis插件](https://gitee.com/jmxd/spider-flow-redis)
- [x] [OSS插件](https://gitee.com/jmxd/spider-flow-oss)
- [x] [Mongodb插件](https://gitee.com/jmxd/spider-flow-mongodb)
- [ ] Hbase插件
- [x] [IP代理池插件](https://gitee.com/jmxd/spider-flow-proxypool)
- [x] [OCR识别插件](https://gitee.com/jmxd/spider-flow-ocr)
- [x] [电子邮箱插件](https://gitee.com/jmxd/spider-flow-mailbox)

### 项目部分截图
![GVP项目爬虫测试](https://images.gitee.com/uploads/images/2019/1030/104033_0075e463_297689.gif "spider-test.gif")
![数据展示](https://images.gitee.com/uploads/images/2019/0716/184618_21bce697_297689.png "demo-2.png")

### 如有问题或者建议请提Issue

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)