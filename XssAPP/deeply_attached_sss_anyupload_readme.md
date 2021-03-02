# anyupload

[![Build Status](https://travis-ci.org/dianbaer/anyupload.svg?branch=master)](https://travis-ci.org/dianbaer/anyupload)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/5418a2ab4049430cb9f58510ec28f452)](https://www.codacy.com/app/232365732/anyupload?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=dianbaer/anyupload&amp;utm_campaign=Badge_Grade)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)


### anyupload是一个极度纯净的上传插件，通过简单调整就可以融入到任何项目，支持多文件上传、上传速率动态控制、真实进度监控kb/s、分块生成MD5、分块上传、MD5校验秒传、暂停、取消等。



### 体验地址：

https://www.dianbaer.com/AnyUploadClient/


![上传图](./anyupload.png "anyupload.png")


![流程图](./anyuploadflow.png "anyuploadflow.png")


## 项目目录结构：

	
### AnyUploadClient（1000行代码）

	|--js（js库）
		|--anyupload（anyupload文件夹）
			|--css（anyupload css）
			|--dist（anyupload js打包版本）
			|--images（anyupload image）
			|--src（anyupload js未打包版本）
				|--FileConfig.js（配置）
		|--lib（依赖js）
			|--jquery.min.js
			######################################
			|--juggle-all.js（解耦合的工具库ALL IN ONE：https://github.com/dianbaer/juggle）
			或
			|--juggle-help.js
			|--juggle-event.js
			|--juggle-juggler.js    （解耦合的工具库small require：https://github.com/dianbaer/juggle）
			|--juggle-http.js
			|--juggle-mv.js
			######################################
			|--spark-md5.js（用于分块计算md5）
	|--index.html（示例启动项目）


### AnyUploadServer（899行代码）

	|--src（服务器代码）
		|--CommonConfig.java（配置）
	|--protobuf（消息包生成工具）


### AnyUploadClient怎么使用：

```html

 
 
 
     
      
     
      
    -->
     
      
      
      
      
      
     
      
      
     
     
      

 
 
    var fileMediator;
    /**
     * 选择文件时的响应
     * @param e
     */
    var uploadFileButtonChange = function (e) {
        if (!("FileReader" in window) || !("File" in window)) {
            alert("您的浏览器不支持html5，请使用google，firefox，ie10等浏览器");
            return;
        }
        var files = e.target.files;
        //调用anyupload上传函数
        fileMediator.upLoadFile(files);
        //清空上传按钮的内容
        $("#uploadFileButton").val("");
    };
    window.onload = function () {
        /****初始化anyupload开始*****/
        fileMediator = new anyupload.FileMediator();
        //设置anyupload的容器对象
        fileMediator.initView($("#anyUploadContainer"));
        //设置anyupload的上传地址
        anyupload.uploadFileProxy.url = "http://localhost:8080/AnyUploadServer/s";
        /****初始化anyupload结束*****/
        $("#uploadFileButton").on("change", uploadFileButtonChange);

    }
 
 
 
 
 
  
 
 


```

### AnyUploadClient js源码打包


	cd AnyUploadClient/js/anyupload
	
	npm install -g grunt-cli

	npm install
	
	grunt
	


### AnyUploadServer怎么使用

	如果测试，直接启动AnyUploadServer即可，不需要修改配置
	
	如果融入其他项目，按照AnyUploadServer代码示例需要提供两个接口
	
	message MD5CheckC{
		string hOpCode=1;
		string fileBaseMd5=2;//md5
		string userFileName=3;//文件名
		string userFoldParentId=4;//父类文件夹id
		int64 fileBaseTotalSize=5;//文件总大小
		string userFileId=6;//文件id
	}
	message MD5CheckS{
		string hOpCode=1;
		int32 result=2;//结果1：秒传，2：可以上传
		int64 fileBasePos=3;//开始位置
		int32 uploadMaxLength=4;//一次上传最大长度
		string userFileId=5;//文件id
	}
	message UploadFileC{
		string hOpCode=1;
		string userFileId=2;//文件id
		int64 fileBasePos=3;//开始位置
		int32 uploadLength=4;//上传的长度
	}
	message UploadFileS{
		string hOpCode=1;
		int32 result=2;//结果1：秒传，2：可以上传，3上传完成
		int64 fileBasePos=3;//开始位置
		int32 uploadMaxLength=4;//一次上传最大长度
		string userFileId=5;//文件id
		int32 waitTime=6;//等待时间
	}
	
### AnyUploadServer打包


	ant

	


### java服务器基于grain

依赖以下库，共（1429行，学习成本极低）

	grain-httpserver.jar（1318行）
	grain-log.jar（111行）


github：


https://github.com/dianbaer/grain


码云：


https://gitee.com/dianbaer/grain


### js客户端基于juggle

最精简依赖以下库，共（614行，学习成本极低）

	juggle-help.js（33行）
	juggle-event.js（256行）
	juggle-http.js（99行）
	juggle-mv.js（104行）
	juggle-juggler.js（122行）

github：


https://github.com/dianbaer/juggle


码云：


https://gitee.com/dianbaer/basic




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)