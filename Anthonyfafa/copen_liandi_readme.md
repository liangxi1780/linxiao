 
 
 
 链滴笔记，连接点滴 
  
   
   
   
 
   
   
   
 
   
   
   
   
  
     
     
     
   
 

## 💡 简介

链滴笔记是一款开源的桌面端笔记应用，支持 Windows、Mac 和 Linux。

### ✨  特性

* 为 Markdown 而生
  * 支持传统的分屏编辑预览模式
  * 支持类似 Typora 保留标记符的实时渲染模式 `TBD`
  * 支持所见即所得编辑模式
  * 支持数学公式、图表、流程图、甘特图、时序图、五线谱等
  * Markdown 文本格式化
  * 粘贴 HTML 自动转换为 Markdown
  * 配置 Markdown 解析渲染细节参数
    * 是否启用脚注支持 `TBD`
    * 是否启用 [ToC] 支持 `TBD`
    * 是否需要中西文间自动插入空格
    * 是否进行自动术语修正
    * 中文后跟英文逗号句号等标点是否自动替换为中文对应标点
    * 内联数学公式是否允许起始 $ 后紧跟数字
    * 数学公式引擎切换 MathJax、Ketax
* WebDAV 挂载远程目录
* Double Shift 快速导航
* 全文搜索
* 明亮、暗黑两套主题
* 标签聚合分类 `TBD`
* 导出静态站点，内置多套主题 `TBD`

## 📸 截图

### 明亮主题

![white](https://user-images.githubusercontent.com/873584/74507339-11e16080-4f37-11ea-8700-e9d4ebfa9787.png)

### 暗黑主题

![dark](https://user-images.githubusercontent.com/873584/74507336-0ee67000-4f37-11ea-827c-903644d0de3e.png)

### Markdown 配置

![dark-md](https://user-images.githubusercontent.com/873584/74507501-89af8b00-4f37-11ea-9de2-534aed8c2c78.png)

### 全文搜索

![dark-search](https://user-images.githubusercontent.com/873584/74507506-8c11e500-4f37-11ea-9ff2-b1c41b3be225.png)

## 🛠️ 安装

### 安装包

* [GitHub](https://github.com/88250/liandi/releases)
* [码云](https://gitee.com/dl88250/liandi/releases)
* [本地下载](https://liandi.b3log.org/releases)

#### 源码构建

1. 安装 Go、Node 环境
2. 运行项目根目录下的 build 脚本 
3. 构建成功后将在 app/build 下生成安装包

如果你要修改源码，请按如下步骤搭建开发环境：

1. 在 kernel 目录下构建内核并启动
   * Windows：`go build -o kernel.exe && kernel.exe`
   * Mac：`go build -o kernel-darwin && ./kernel-darwin`
   * Linux：`go build -o kernel-linux && ./kernel-linux`
2. 在 app 目录下构建前端 `npm run dev` 并启动主进程 `npm run start`

## 🏗️ 技术架构

![链滴笔记架构图](https://user-images.githubusercontent.com/873584/73417483-2e847280-4353-11ea-9e4c-2594c4b08b35.png)

* 通过 Electron 实现主进程，启动后拉起 golang 实现的内核进程
* 内核实现 WebSocket 服务端和主进程交互
* 内核实现 WebDAV 服务端和客户端
* 文件存取（包括操作本地文件）通过 WebDAV 客户端进行
* Markdown 文件启动和挂载时加载到内存实现全文搜索
* 通过 Vditor 编辑器实现 Markdown 所见即所得编辑模式

## 📜 文档

* [链滴笔记路线图](https://hacpai.com/article/1579786655216)

## 🏘️ 社区

* [讨论区](https://hacpai.com/tag/liandi-biji)
* [报告问题](https://github.com/88250/liandi/issues/new)
* 欢迎关注 B3log 开源社区微信公众号 `B3log开源`  
  ![image-d3c00d78](https://user-images.githubusercontent.com/873584/71566370-0d312c00-2af2-11ea-8ea1-0d45d6f0db20.png)

## 📄 开源协议

链滴笔记使用 [木兰宽松许可证, 第2版](http://license.coscl.org.cn/MulanPSL2) 开源协议。

## 🙏 鸣谢

* [浏览器端的编辑器 Vditor](https://github.com/Vanessa219/vditor)
* [对中文语境优化的 Markdown 引擎 Lute](https://github.com/88250/lute)
* [Go WebDAV 客户端库](https://github.com/88250/gowebdav)
* [Go 常用工具库](https://github.com/88250/gulu)
* [Go Web 框架 Gin](https://github.com/gin-gonic/gin)
* [Go WebSocket 框架 melody](https://github.com/olahol/melody)
* [跨平台桌面应用框架 Electron](https://github.com/electron/electron)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)