# ebookdownloader
网文下载器

 [![GitHub license](https://img.shields.io/github/license/sndnvaps/ebookdownloader)](https://github.com/sndnvaps/ebookdownloader/blob/master/LICENSE)

[![Build Status](https://travis-ci.org/sndnvaps/ebookdownloader.svg?branch=master)](https://travis-ci.org/sndnvaps/ebookdownloader)[![release_version](https://img.shields.io/github/release/sndnvaps/ebookdownloader.svg)](https://github.com/sndnvaps/ebookdownloader/releases)[![Download Count](https://img.shields.io/github/downloads/sndnvaps/ebookdownloader/total.svg)](https://github.com/sndnvaps/ebookdownloader/releases)



[![godoc](https://img.shields.io/badge/godoc-reference-blue.svg)](https://godoc.org/github.com/sndnvaps/ebookdownloader/)

# ebookdl 网文下载器，go语言版本

  ## 安装方法
  ```bash
  go get github.com/sndnvaps/ebookdownloader/cli
  go get github.com/sndnvaps/ebookdownloader/gui
  go get github.com/sndnvaps/ebookdownloader/http-server
  ```
  ## 使用方法
  ```bash
  .\ebookdownloader.exe --bookid=0_642 --txt #只生成txt文本
  .\ebookdownloader.exe --bookid=0_642 --mobi #只生成mobi电子书
  .\ebookdownloader.exe --bookid=0_642 --txt --mobi #生成txt 和 mobi
  .\ebookdownloader.exe --bookid=0_642 --txt --awz3 #生成txt 和 awz3
  .\ebookdownloader.exe --proxy="http://proxyip:proxyport" --bookid=0_642 --mobi #生成mobi电子书，在下载章节的过程中使用 Proxy
  .\ebookdownloader.exe --ebhost=xsbiquge.com --bookid=0_642 --txt --mobi #使用xsbiquge.com做为下载源，生成txt 和 mobi
  .\ebookdownloader.exe --ebhost=999xs.com --bookid=0_642 --txt --mobi #使用999xs.com做为下载源，生成txt 和 mobi
   .\ebookdownloader.exe --ebhost=999xs.com --bookid=0_642 --txt --mobi --meta #使用999xs.com做为下载源，生成txt,mobi电子书，并生成meta.json文件于小说目录当中
  .\ebookdownloader.exe --ebhost=23us.la --bookid=127064 --pv #新功能，用于打印小说的分卷信息，此时不下载小说任何内容
  .\ebookdownloader.exe --bookid=0_0642 --json #生成json格式的小说数据
  .\ebookdownloader.exe conv --json=".\outputs\我是谁-sndnvaps\我是谁-sndnvaps.json" --txt --mobi #新功能，转换json格式到txt,mobi格式
  .\ebookdownloader.exe --help #显示帮助信息
  ```

  ## 依赖程序 
    1. kindlegen.exe 支持windows平台
    2. kindlegenLinux 支持Linux 平台
    3. kindlegenMac 支持 Mac平台
    4. cli/gui 两个项目，都需要在当前项目的根目录运行
    5. gui程序，需要依赖 https://github.com/akavel/rsrc ，项目来生成图标
    6. qemu-i386-static-armhf 支持在linux arm平台上运行 kindlegenLinux
    7. qemu-i386-static-arm64 支持在linux arm64平台上运行 kindlegenLinux
    8. http-server 项目依赖：
          github.com/ajvb/kala 项目，用于任务控制和管理
          kala需要与ebookdownloader_cli运行在同一个目录里面

  ## 后端服务器 API接口
    主要目的是部署在vps上面，就可以方便随时下载小说了
   API接口文档
[ebookdownloader_http_api](http-server/ebookdownloader_http_api.md)

配置文件[ebdl_conf.ini](conf/ebdl_conf.ini)

  ## 懒人模式，直接下载编译好的程序
  
  墙里面使用gitee

  [gitee ebookdownloader release page](https://gitee.com/sndnvaps/ebookdownloader/releases "https://gitee.com/sndnvaps/ebookdownloader/releases")

墙外面使用github

  [github ebookdownloader release page](https://github.com/sndnvaps/ebookdownloader/releases "https://github.com/sndnvaps/ebookdownloader/releases")


  ## 更新日志
  
      2020.02.14 go版本
                1. http-server:添加创建任务功能和查询任务功能（使用kala Job Schedule)
                2. 对代码进行添加注释
                3. 添加新接口 GetBookBriefInfo只用于获取小说名字，作者，简介信息
                4. gui: 更新代码，修改字体的路径
                5. gui: 现在改用外部调用ebookdownloader_cli来执行下载操作，需要用到配置文件./conf/ebdl_conf.ini

      2020.02.13 go版本
                1. cli: 重新补充完成meta.json信息

      2020.02.12 go版本
                1. 添加gitee项目地址，加快国内的下载速度
                2. 生成txt：修改方法为按一章一章地往磁盘中写入文件，以降低cpu占用率
                3. cli: 添加生成json格式内容，用于把小说保存成json格式，方便线下再进行转换，方便进行二次处理
                4. 添加二级命令conv,用于转换json文件到txt,mobi,azw3格式小说

      2020.02.10 go版本
                1. 添加小说章节分割下载功能(以300章为一个下载单元)
                2. 限制并发数量，目前最大并发数量为 (300+49)*2 = 698
                3. arm版本问题：目前只能生成txt文件，因为生成mobi花费时间过于长(测试平台:Raspberry Pi 3b, cpu过于垃圾和内存太小)
                4. 更新版本到 v1.7.1
                5. 更换字体为: 文泉驿微米黑 Regular

     2020.02.02 go版本
                1. 初步添加kala接口，做为 Job Scheduler
                2. cli版本添加生成meta.json文件功能

     2020.01.28 go版本
                1. ebookdownloader 修改获取章节的规则:替换   为 \r\n
                2. http-server 添加鉴权功能，通过/login来获取 token

      2020.01.27 go版本
                1. http-server添加中文件，处理跨域访问问题
                2. 修改小说下载后，保存目录为 ./outputs/小说名-作者/
                3. http-server 添加生成meta.json,用于保存小说作者，小说简介，小说下载网站，小说bookid等信息
                4. http-server 配置文件修改，原来的host定义为外部地址，iner_host定义为内部地址
                
      2020.01.26 go版本
                1. 添加 http-server版本，初始化
                2. 添加qemu-i386-static 支持arm,arm64平台上生成mobi,azw3格式电子书
                3. 更新版本到 v1.7.0

      2020.01.24 go版本
                1. 版本更新到 v1.6.3
                2. 更新到 v1.6.4 用于测试 Travis-ci
      2020.01.23 go版本 更新
                 1. 使用 github.com/AllenDang/giu 库，重新构建 gui界面
                 2. 编译命令 cd gui;build.[cmd|sh]。文件生成后，会复制到根目录
                 
      2020.01.22 go版本 更新
                 1. 分离出命令行版本cli,编译命令 cd cli;build.[cmd|sh]。文件生成后，会复制到根目录
                 2. 界面版本gui,立项目
                 3. 添加go mod支持

      2020.01.13 go版本 更新
                 1. 修复潜在问题，无法生成 ./outputs目录
                 2. 修复azw3后序出错问题，已经可以在 calibre中阅读
                 3. 版本升级为 v1.6.1
                 感谢 @Biercenter 的反馈

      2020.01.08 go版本 更新
                 1. 版本升级为 v1.6.0
                 2. 完成生成二级目录功能(目前只有顶点小说网支持这个功能)
                 3. 修改下载章节的方法，现在使用 gorountine,多并发下载
                 
      2020.01.06 go版本 更新
                 1. 添加顶点小说 23us.la支持
                 2. 初始支持把分卷信息写入相应的volumes结构体当中（还没有正式测试生成二级目录功能)
                 
      2020.01.05 go版本 更新
                 1. 实现二级目录直接写入 tpl_*.html文件当中
                 2. 添加tpl/tpl_volume.html 用于生成目录分卷
                 3. 实现mobi格式二级目录的生成（网站捉取二级目录部分，正在努力实现）

      2020.01.04 go版本 更新
                 1. 初始化 kindle二级目录支持代码(具体功能还在实现)
                 2. 更新ebookdl_test.go: 实例化 二级目录txt支持
                 
      2020.01.03 go版本 更新
                  1. 修改生成电子书的压缩比为-c2,使生成的文件更小
                  2. 添加生成awz3格式支持(注意，--mobi,--awz3只能使用一个，不能同时使用)
                  3. 修改封面的引用方法

      2019.12.29 go版本 完成实现 999xs.com平台的小说下载接口

      2019.12.27 go版本 实现不同小说平台的interface{}接口，方便加入新的小说网站

      2019.12.25 go版本 修改小说名字排版方式为坚排

      2019.12.22 go版本添加 
                 1. 简单代码测试
                 2. 使用图片格式的封面，方便后面使用 calibre更换封面

      2019.12.9 go版本添加 代理支持

      2019.12.8 go版本添加 Linux,Mac系统支持

      2019.12.6 go版本添加 进度条功能

      2019.12.5 添加go语言版本支持
      
      2019.8.22 python版本初始化

  ## To Do List

     [√]  1. 添加生成封面功能
     [√]  2. 添加不同平台的接口实现
     [√]  3. 添加生成二级目录的方法(已经添加相应的实例)
     [√]  4. 添加界面版本gui
     [√]  5. 添加http-server,做为后端
     [√]  6. 添加linux arm,arm64平台支持
     [√]  7. 需要限制并发数量，因为vps性能有限 -> 目前限制的并发数量为(300+49)*2 = 698


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)