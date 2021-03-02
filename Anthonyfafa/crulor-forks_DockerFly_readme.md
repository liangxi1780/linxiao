![DockerFly](http://git.oschina.net/uploads/images/2017/0227/130240_f5a011b5_116083.png "DockerFly")
------------------

#####Dockerfly是基于 Docker1.12+ (Docker API 1.24+) 开发出Docker 管理工具,提供里最基本的基于 Docker 的管理功能,目的是能够方便广大Docker初学者以及 Docker 管理员能够快速的进行Docker 容器的管理和维护。
------------------
> 使用 dockerfly 可以管理docker中 swarm、container、network、volume、image 等等你在 docker 中想管理的所有东西。

> 通过 dockerfly 的swarm管理你可以轻松的构建起一个基于 Docker 原生的集群系统。

> 当然首先你要懂 Docker 不要拿他当虚拟机。

**交流QQ群：**454201740

------------------
###最新版本:
 - `20170526`
   - 增加了用户管理和基本的权限控制
   - 增加了 Registry 的管理
   - 增加容器重命名操作
   - 为容器增加 kill 操作
   - Image增加从 Registry 中 pull 镜像的功能
   - 增加了直接从 Image 管理页面创建容器和服务的功能
   - 其他优化 和 bug 修复, 具体请查看 release


 - `20170508`
   - 界面风格显示优化
   - 本次新增功能：
       - 1.容器展示增加:Commit, 网络的Connect和Disconnect。
       - 2.容器创建增加自动从镜像获取必要的信息默认到容器创建的参数,如镜像要求的端口、卷等。
       - 3.增加镜像、网络、卷、服务、的信息展示。
   - 增加了更多的服务和容器的创建选项。
   - 对于用时长的操作（如:镜像搜索,镜像拉去）采用了异步的形式。
   - 修复容器日志显示重复内容的问题。
   - 更新 JDocker 和 voovan 到最新版本。



 - `20170227` 首个发布版本

####请在 pull 的时候,替换版本号 。####

------------------

####feature:
#####自发布之日起,得到了各位朋友的支持,也给我了更多的信心,我会持续支持本项目的开发。
#####有新的建议大家可以用 feature 标签 提交 issues,我会根据功能的相互依赖性以及其使用的广泛型,编排版本.

 - ~~权限管理，每个用户只能管理自己创建的容器、服务、卷、网络等资源。~~
 - ~~服务节点管理所有加入该服务节点的容器、卷等等资源。~~
 - ~~Registry导入镜像和 Registry 服务管理。~~



------------------
###使用方法
 - Clone 后在本地使用
```shell
git clone https://git.oschina.net/helyho/DockerFly.git
cd DockerFly
./start.sh
```
    > `start.sh` 脚本依赖 socat,所以请您先安装 socat 到您的系统中,或者您已经暴露了一个 docker 的 TCP 端口,请删除对应的命令。并访问:http://127.0.0.1:28083 在 setting 页面配置您的 ip 和 端口。

    > `Ubuntu安装socat`: shell sudo apt-get install socat

    > `Centos安装socat`: shell yum install -y socat

 - 直接 pull 一个 dockerfly 容器
```shell
    docker pull helyho/dockerfly[: ]
    docker run \
            --name dockerfly -d \
            -v /var/run/docker.sock:/var/run/docker.sock \
            --restart always \
            -p 28083:28083 \
    helyho/dockerfly
```
    访问:http://127.0.0.1:28083, 使用: `admin` / `1234` 登录到 dockerfly

------------------

####容器操作
![输入图片说明](https://git.oschina.net/uploads/images/2017/0510/160224_3efe4007_116083.png "在这里输入图片标题")
####容器资源
![输入图片说明](https://git.oschina.net/uploads/images/2017/0510/160205_e463d60d_116083.png "在这里输入图片标题")
####容器状态
![输入图片说明](https://git.oschina.net/uploads/images/2017/0510/160215_d527a3d4_116083.png "在这里输入图片标题")
####创建容器
![输入图片说明](https://git.oschina.net/uploads/images/2017/0510/160235_96f70ca0_116083.png "在这里输入图片标题")
####创建服务
![输入图片说明](https://git.oschina.net/uploads/images/2017/0510/160244_e717f8a4_116083.png "在这里输入图片标题")
####拉取镜像
![输入图片说明](https://git.oschina.net/uploads/images/2017/0510/160253_ea6d3140_116083.png "在这里输入图片标题")

------------------

###相关项目
Dockerfly 是一个开源项目Voovan 的子项目,如果您觉得软件好用请推广给你的朋友并请您抽出宝贵时间 Star 一下项目。感谢各位的支持！！！

**Voovan项目**
 - [https://git.oschina.net/helyho/Voovan](https://git.oschina.net/helyho/Voovan) 

**JDocker:**
 - [https://git.oschina.net/helyho/JDocker](https://git.oschina.net/helyho/JDocker)

**Vestful:**
 - [https://git.oschina.net/helyho/Vestful](https://git.oschina.net/helyho/Vestful)

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)