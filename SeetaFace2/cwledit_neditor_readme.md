
## Neditor富文本编辑器介绍

Neditor 是我们团队基于 Ueditor 的一款富文本编辑器。
不论从功能还是从其它各方面来讲， Ueditor 都是一款无以替代的编辑器产品。
只是已经不符合现代化样式的需求，于是我们修改它的样式，实现了这样的效果：

![image](https://www.notadd.com/src/neditor.webp)

Demo:  https://neditor.notadd.com/demo/

## 入门部署和体验 ##

### 第一步：下载编辑器 ###

下载 Neditor 最新版

或从源码编译：

```shell
git clone 仓库地址
npm install
grunt notadd
```

### 第二步：创建 demo 文件 ###

解压下载的包，在解压后的目录创建 demo.html 文件，填入下面的 html 代码

```html
 
 
 
	 
	 ueditor demo 
 
 
	 
	 这里写你的初始化内容 
	 
	  
	 
	  
	 
	 
	    var ue = UE.getEditor('container');
	 
 
 
```

### 第三步：在浏览器打开demo.html ###

如果看到了下面这样的编辑器，恭喜你，初次部署成功！

![部署成功](https://www.notadd.com/src/neditor-demo.webp)

### 自定义的参数

编辑器有很多可自定义的参数项，在实例化的时候可以传入给编辑器：

```javascript
var ue = UE.getEditor('container', {
    autoHeight: false
});
```

配置项也可以通过 neditor.config.js 文件修改，具体的配置方法请看[前端配置项说明](http://fex.baidu.com/ueditor/#start-config1.4 前端配置项说明.md)

### 设置和读取编辑器的内容

通 getContent 和 setContent 方法可以设置和读取编辑器的内容

```javascript
var ue = UE.getContent();
ue.ready(function(){
    //设置编辑器的内容
    ue.setContent('hello');
    //获取html内容，返回:  hello 
    var html = ue.getContent();
    //获取纯文本内容，返回: hello
    var txt = ue.getContentTxt();
});
```

Ueditor 的更多API请看[API 文档](http://ueditor.baidu.com/doc "ueditor API 文档")

## 相关链接 ##

Ueditor 官网：[http://ueditor.baidu.com](http://ueditor.baidu.com "ueditor 官网")

Ueditor API 文档：[http://ueditor.baidu.com/doc](http://ueditor.baidu.com/doc "ueditor API 文档")

Ueditor github 地址：[http://github.com/fex-team/ueditor](http://github.com/fex-team/ueditor "ueditor github 地址")

Neditor github 地址：[http://github.com/notadd/neditor](http://github.com/fex-team/ueditor "Neditor github 地址")

## 详细文档

Ueditor 文档：[http://fex.baidu.com/ueditor/](http://fex.baidu.com/ueditor/)

注: 对IE8以下版本不再承诺兼容

## 联系我们 ##

QQ 群： 321735506
issue：[github issue](http://github.com/notadd/neditor/issues "ueditor 论坛")

## 捐赠 


[捐赠](https://git.oschina.net/notadd/notadd?donate=true)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)