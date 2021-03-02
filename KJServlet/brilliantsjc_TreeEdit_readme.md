# TreeEdit

Qml实现的树结构编辑器。

|功能|进度|tag|
|--|--|--|
|树结构的缩进|完成|0.1.0|
|展开、折叠|完成|0.1.0|
|添加|完成|0.1.0|
|删除|完成|0.1.0|
|重命名|完成|0.1.0|
|搜索|完成|0.1.0|
|导入|完成|0.2.0|
|导出|完成|0.2.0|
|性能测试|支持|master|
|节点属性编辑|计划中|

## 原理

View 使用qml中的 Controls2 ListView

Model使用C++中的 QAbstractListModel子类

model中增加额外数据，表示树结构的深度、父子关系等，view通过额外数据显示、处理。

## Qt版本

5.12.x

## Build

| [Windows][win-link]| [Ubuntu][ubuntu-link]|[MacOS][macos-link]|[Android][android-link]|[IOS][ios-link]|
|---------------|---------------|-----------------|-----------------|----------------|
| ![win-badge]  | ![ubuntu-badge]      | ![macos-badge] |![android-badge]   |![ios-badge]   |


[win-link]: https://github.com/JaredTao/TreeEdit/actions?query=workflow%3AWindows "WindowsAction"
[win-badge]: https://github.com/JaredTao/TreeEdit/workflows/Windows/badge.svg  "Windows"

[ubuntu-link]: https://github.com/JaredTao/TreeEdit/actions?query=workflow%3AUbuntu "UbuntuAction"
[ubuntu-badge]: https://github.com/JaredTao/TreeEdit/workflows/Ubuntu/badge.svg "Ubuntu"

[macos-link]: https://github.com/JaredTao/TreeEdit/actions?query=workflow%3AMacOS "MacOSAction"
[macos-badge]: https://github.com/JaredTao/TreeEdit/workflows/MacOS/badge.svg "MacOS"

[android-link]: https://github.com/JaredTao/TreeEdit/actions?query=workflow%3AAndroid "AndroidAction"
[android-badge]: https://github.com/JaredTao/TreeEdit/workflows/Android/badge.svg "Android"

[ios-link]: https://github.com/JaredTao/TreeEdit/actions?query=workflow%3AIOS "IOSAction"
[ios-badge]: https://github.com/JaredTao/TreeEdit/workflows/IOS/badge.svg "IOS"

## Release

|[许可][license-link]|[已发布][release-link]|[下载][download-link]|下载次数|
|:--:|:--:|:--:|:--:|
|![license-badge]|![release-badge] |![download-badge]|![download-latest]|


[license-link]: https://github.com/jaredtao/TreeEdit/blob/master/LICENSE "LICENSE"
[license-badge]: https://img.shields.io/badge/license-MIT-blue.svg "MIT"
[release-link]: https://github.com/jaredtao/TreeEdit/releases "Release status"
[release-badge]: https://img.shields.io/github/release/jaredtao/TreeEdit.svg?style=flat-square "Release status"
[download-link]: https://github.com/jaredtao/TreeEdit/releases/latest "Download status"
[download-badge]: https://img.shields.io/github/downloads/jaredtao/TreeEdit/total.svg "Download status"
[download-latest]: https://img.shields.io/github/downloads/jaredtao/TreeEdit/latest/total.svg "latest status"

## 性能测试

### 测试环境

CPU: Intel i5-8400 2.8GHz

内存: 16GB

OS: Windows10 1909

Qt: 5.12.6

编译器: msvc 2017 x64

测试框架: QTest

### 测试结果

|节点数量|嵌套数量|导入平均耗时(毫秒)|导出平均耗时(毫秒)|
|--|--|--|--|
|1|1|0.050|0.96|
|1|10|0.089|5.15|
|1|100|0.57|12|
|10|1|0.10|3.7|
|10|10|0.42|6.0|
|10|100|5.1|79.5|
|100|1|0.65 |6.6|
|100|10|3.8|40.0|
|100|100|59|468|
|1000|1|5.8 |33|
|1000|10|37 |108|
|1000|100|671 |3765|
|10000|1|59 |74|
|10000|10|386 |823|
|10000|100|6720 |39563|



## 效果预览

### 软件界面

![](preview/preview.png)

### 导入

![](preview/import.gif)

### 搜索

![](preview/find.gif)

### 创建

![](preview/create.gif)

### 删除

![](preview/delete.gif)

### 重命名

![](preview/rename.gif)

### 折叠和展开

![](preview/expo.gif)

### 清空

![](preview/clear.gif)

### 导出

![](preview/save.gif)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)