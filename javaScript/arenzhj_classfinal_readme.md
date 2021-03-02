# ClassFinal

## 介绍
ClassFinal是一款java class文件安全加密工具，支持直接加密jar包或war包，无需修改任何项目代码，兼容spring-framework；可避免源码泄漏或字节码被反编译。

##### Gitee: https://gitee.com/roseboy/classfinal

## 项目模块说明
* **classfinal-core:** ClassFinalde的核心模块，几乎所有加密的代码都在这里；
* **classfinal-fatjar:** ClassFinal打包成独立运行的jar包；
* **classfinal-maven-plugin:** ClassFinal加密的maven插件；

## 功能特性
* 无需修改原项目代码，只要把编译好的jar/war包用本工具加密即可。
* 运行加密项目时，无需求修改tomcat，spring等源代码。
* 支持普通jar包、springboot jar包以及普通java web项目编译的war包。
* 支持spring framework、swagger等需要在启动过程中扫描注解或生成字节码的框架。
* 支持maven插件，添加插件后在打包过程中自动加密。
* 支持加密WEB-INF/lib或BOOT-INF/lib下的依赖jar包。

## 环境依赖
JDK 1.8 +

## 使用说明

### 下载
[点此下载](http://repo.maven.apache.org/maven2/net/roseboy/classfinal-fatjar/1.1.3/classfinal-fatjar-1.1.3.jar)

### 加密

执行以下命令

```sh
java -jar classfinal-fatjar.jar -file yourpaoject.jar -libjars a.jar,b.jar -packages com.yourpackage,com.yourpackage2 -exclude com.yourpackage.Main -pwd 123456 -Y
```

```text
参数说明
-file        加密的jar/war完整路径
-packages    加密的包名(可为空,多个用","分割)
-libjars     jar/war包lib下要加密jar文件名(可为空,多个用","分割)
-exclude     排除的类名(可为空,多个用","分割)
-pwd         加密密码
-Y           无需确认，不加此参数会提示确认以上信息
```

结果: 生成 yourpaoject-encrypted.jar，这个就是加密后的jar文件；加密后的文件不可直接执行，需要配置javaagent。

> 注:
> 以上示例是直接用参数执行，也可以直接执行 java -jar classfinal-fatjar.jar按照步骤提示输入信息完成加密。

### maven插件方式

在要加密的项目pom.xml中加入以下插件配置,目前最新版本是：1.1.3。
```xml
 
     net.roseboy 
     classfinal-maven-plugin 
     ${classfinal.version} 
     
         000000  
         com.yourpackage,com.yourpackage2 
         org.spring 
         a.jar,b.jar 
     
     
         
             package 
             
                 classFinal 
             
         
     
 
```
运行mvn package时会在target下自动加密生成yourpaoject-encrypted.jar。

maven插件的参数名称与直接运行的参数相同，请参考上节的参数说明。

### 启动加密后的jar

加密后的项目需要设置javaagent来启动，项目在启动过程中解密class，完全内存解密，不留下任何解密后的文件。

解密功能已经自动加入到 yourpaoject-encrypted.jar中，所以启动时-javaagent与-jar相同，不需要额外的jar包。

启动jar项目执行以下命令：

```sh
java -javaagent:yourpaoject-encrypted.jar='-pwd 0000000' -jar yourpaoject-encrypted.jar

//参数说明 -pwd   加密项目的密码  
```

或者不加pwd参数直接启动，启动后在控制台里输入密码，推荐使用这种方式：

```sh
java -javaagent:yourpaoject-encrypted.jar -jar yourpaoject-encrypted.jar
```


### tomcat下运行加密后的war

将加密后的war放在tomcat/webapps下，
tomcat/bin/catalina 增加以下配置:

```sh
//linux下 catalina.sh
CATALINA_OPTS="$CATALINA_OPTS -javaagent:classfinal-fatjar.jar='-pwd 0000000'";
export CATALINA_OPTS;

//win下catalina.bat
set JAVA_OPTS="-javaagent:classfinal-fatjar.jar='-pwd 000000'"

//参数说明 -pwd   加密项目的密码  

```

-------------------------

> 本工具使用AES算法加密class文件，密码是保证不被破解的关键，请保存好密码，请勿泄漏。

> 密码一旦忘记，项目不可启动且无法恢复，请牢记密码。

> 本工具加密后，原始的class文件并不会完全被加密，只是方法体被清空，保留方法参数、注解等信息，这是为了兼容spring，swagger等扫描注解的框架；
方法体被清空后，反编译者只能看到方法名和注解，看不到方法的具体内容；当class被classloader加载时，真正的方法体会被解密注入。


## 版本说明
* v1.1.3 加入输入密码的弹框
* v1.1.2 修复windows下加密后不能启动的问题
* v1.1.1 启动jar时在控制台输入密码，无需将密码放在参数中
* v1.1.0 加密jar包时将解密代码加入加密后的jar包，无需使用多余的jar文件
* v1.0.0 第一个正式版发布

## 协议声明
[Apache-2.0](http://www.apache.org/licenses/LICENSE-2.0)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)