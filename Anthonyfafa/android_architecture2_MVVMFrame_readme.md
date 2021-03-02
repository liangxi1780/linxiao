# MVVMFrame

![Image](app/src/main/ic_launcher-web.png)

[![Download](https://img.shields.io/badge/download-App-blue.svg)](https://raw.githubusercontent.com/jenly1314/MVVMFrame/master/app/release/app-release.apk)
[![JitPack](https://jitpack.io/v/jenly1314/MVVMFrame.svg)](https://jitpack.io/#jenly1314/MVVMFrame)
[![CI](https://travis-ci.org/jenly1314/MVVMFrame.svg?branch=master)](https://travis-ci.org/jenly1314/MVVMFrame)
[![CircleCI](https://circleci.com/gh/jenly1314/MVVMFrame.svg?style=svg)](https://circleci.com/gh/jenly1314/MVVMFrame)
[![API](https://img.shields.io/badge/API-16%2B-blue.svg?style=flat)](https://android-arsenal.com/api?level=16)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/mit-license.php)
[![Blog](https://img.shields.io/badge/blog-Jenly-9933CC.svg)](https://jenly1314.github.io/)
[![QQGroup](https://img.shields.io/badge/QQGroup-20867961-blue.svg)](http://shang.qq.com/wpa/qunwpa?idkey=8fcc6a2f88552ea44b1411582c94fd124f7bb3ec227e2a400dbbfaad3dc2f5ad)

MVVMFrame for Android 是一个基于Google官方推出的Architecture Components dependencies （Lifecycle，LiveData，ViewModel，Room）构建的快速开发框架。有了MVVMFrame的加持，从此构建一个MVVM模式的项目变得快捷简单。

## 架构
![Image](image/mvvm_architecture.jpg)

## [Android version](https://github.com/jenly1314/MVVMFrame/tree/android)

## 引入

### Maven：
```maven
 
   com.king.frame 
   mvvmframe 
   1.1.1 
   pom 
 
```
### Gradle:
```gradle
//AndroidX 版本
implementation 'com.king.frame:mvvmframe:1.1.1'

//Android 版本
implementation 'com.king.frame:mvvmframe:1.0.2'
```
### Lvy:
```lvy
 
    
 
```

## 引入的库 （具体对应版本请查看[Versions](versions.gradle)）
```gradle
    //appcompat
    compileOnly deps.appcompat

    //retrofit
    api deps.retrofit.retrofit
    api deps.retrofit.gson
    api deps.retrofit.converter_gson

    //lifecycle
    api deps.lifecycle.runtime
    api deps.lifecycle.extensions
    annotationProcessor deps.lifecycle.compiler

    //room
    api deps.room.runtime
    annotationProcessor deps.room.compiler

    //dagger
    api deps.dagger.dagger
    api deps.dagger.android
    api deps.dagger.android_support
    annotationProcessor deps.dagger.android_processor
    annotationProcessor deps.dagger.compiler

    //log
    api deps.timber

```

###### 如果Gradle出现compile失败的情况，可以在Project的build.gradle里面添加如下：（也可以使用上面的GitPack来complie）
```gradle
allprojects {
    repositories {
        maven { url 'https://dl.bintray.com/jenly/maven' }
    }
}
```


## 示例

集成步骤代码示例 （示例出自于[app](app)中）

Step.1 启用DataBinding，在你项目中的build.gradle的android{}中添加配置：
```gradle
dataBinding {
    enabled true
}
```

Step.2 自定义全局配置(继承MVVMFrame中的FrameConfigModule)
```Java
/**
 * 自定义全局配置
 * @author  Jenly 
 */
public class ConfigModule extends FrameConfigModule {
    @Override
    public void applyOptions(Context context, com.king.frame.mvvmframe.di.module.ConfigModule.Builder builder) {
        builder.baseUrl(Constants.BASE_URL)//TODO 配置Retrofit中的baseUrl
                .retrofitOptions(new RetrofitOptions() {
            @Override
            public void applyOptions(Retrofit.Builder builder) {
                //TODO 配置Retrofit
                //如想使用RxJava
                //builder.addCallAdapterFactory(RxJava2CallAdapterFactory.create())
            }
        })
        .okHttpClientOptions(new OkHttpClientOptions() {
            @Override
            public void applyOptions(OkHttpClient.Builder builder) {
                //TODO 配置OkHttpClient
            }
        })
        .gsonOptions(new GsonOptions() {
            @Override
            public void applyOptions(GsonBuilder builder) {
                //TODO 配置Gson
            }
        });
    }
}
```

Step.3 在你项目中的AndroidManifest.xml中通过配置meta-data来自定义全局配置
```Xml
 
 
```

Step.4 用你项目的Application继承MVVMFrame中的BaseApplication
```Java
/**
 *  MVVMFrame 框架基于Google官方的Architecture Components dependencies 构建，在使用MVVMFrame时，需遵循一些规范：
 *  1.你的项目中的Application中需初始化MVVMFrame框架相关信息，有两种方式处理：
 *      a.直接继承本类{@link BaseApplication}即可；
 *      b.如你的项目中的Application本身继承了其它第三方的Application，因为Java是单继承原因，导致没法继承本类，可参照{@link BaseApplication}类，
 *      将{@link BaseApplication}中相关代码复制到你项目的Application中，在相应的生命周期中调用即可。
 *
 * @author  Jenly 
 */
public class App extends BaseApplication {

    @Override
    public void onCreate() {
        super.onCreate();
        ApplicationComponent appComponent = DaggerApplicationComponent.builder()
                .appComponent(getAppComponent())
                .build();
        //注入
        appComponent.inject(this);

    }


}
```
[Kotlin Demo](https://github.com/jenly1314/KingWeather)

更多使用详情，请查看[app](app)中的源码使用示例或直接查看[API帮助文档](https://jenly1314.github.io/projects/MVVMFrame/doc/)

### 相关开源项目
##### [KingWeather](https://github.com/jenly1314/KingWeather)  一款天气预报APP
##### [EasyChat](https://github.com/yetel/EasyChatAndroidClient) 一款即时通讯APP


## 版本记录

#### v1.1.1：2019-11-4
*  优化部分细节
*  更新编译SDK至29
*  更新Gradle至v5.4.1
*  更新Lifecycle至v2.2.0-rc01
*  更新Room至v2.2.1
*  更新Dagger至v2.25.2
*  更新Retrofit至v2.6.2
*  更新Gson至v2.8.6

#### v1.1.0：2019-7-22
*  更新Dagger至v2.23.2
*  更新Gradle至v5.1.1
*  完全迁移至AndroidX版本

#### v1.0.2：2019-7-22
*  更新Dagger至v2.19
*  为迁移至AndroidX做准备（下一版本将直接发布AndroidX版）

#### v1.0.1：2019-7-9
*  Retrofit更新至v2.6.0

#### v1.0.0：2018-12-12
*  MVVMFrame初始版本

## 赞赏
如果您喜欢MVVMFrame，或感觉MVVMFrame帮助到了您，可以点右上角“Star”支持一下，您的支持就是我的动力，谢谢 :smiley: 
您也可以扫描下面的二维码，请作者喝杯咖啡 :coffee:
     
         
         
         
         
     

## 关于我
   Name:  Jenly 

   Email:  jenly1314#gmail.com  /  jenly1314#vip.qq.com 

   CSDN:  jenly121 

   博客园:  jenly 

   Github:  jenly1314 

   加入QQ群:  20867961 
    
        
        
    


   


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)