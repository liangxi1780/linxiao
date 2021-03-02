# FaceMaskDetection
**检测人脸并判断是否佩戴了口罩**

Detect faces and determine whether they are  wearing mask.

**首先，祝愿我国和世界各国早日战胜新冠肺炎疫情，武汉加油！中国加油！**

*  我们开源了人脸口罩检测的**Keras模型**以及**caffe模型**（keras模型转换得到的），并提供了Keras的运行代码和Caffe的运行代码（训练代码我们整理好后会立即开源）。模型在`models`文件夹下。


* 开源了标注的7959张人脸标注图片，数据集来自于[WIDER Face](http://shuoyang1213.me/WIDERFACE/)和[MAFA](http://www.escience.cn/people/geshiming/mafa.html)数据集, 我们重新修改了标注并进行了校验(主要是
MAFA和WIDER Face的人脸位置定义不一样，所以我们进行了修改标注)并将其开源出来。（有需要的朋友，敬请关注我们新建的公众号AIZOO（本文末也有二维码，可以扫描关注），回复**口罩数据集**就可以了。公众号刚开，恳请大家帮忙关注和扩散一下～）


![](/img/demo.png)
## 模型结构
我们在本项目中使用了SSD类型的架构，为了让模型可以实时的跑在浏览器以及终端设备上，我们将模型设计的非常小，只有101.5万个参数。模型结构在本文附录部分。

本模型输入大小为260x260，主干网络只有8个卷积层，加上定位和分类层，一共只有24层（每层的通道数目基本都是32\64\128），所以模型特别小，只有101.5万参数。模型对于普通人脸基本都能检测出来，但是对于小人脸，检测效果肯定不如大模型。具体效果，大家可以点击以下链接，访问我们的网站在线体验效果。
[aizoo.com跑在您浏览器的口罩检测模型](https://aizoo.com/face-mask-detection.html)

网页使用了Tensorflow.js库，所以模型是完全运行在您浏览器里面的。运行速度的快慢，取决于您电脑配置的高低。

模型在五个卷积层上接出来了定位分类层，其大小和anchor设置信息如下表.


| 卷积层 | 特征图大小 | anchor大小 | anchor长宽比（aspect ratio）|
| ---- | ---- | ---- | ---- |
|第一层|33x33|0.04,0.056|1,0.62,0.42|
|第二层|17x17|0.08,0.11|1,0.62,0.42|
|第三层|9x9|0.16,0.22|1,0.62,0.42|
|第四层|5x5|0.32,0.45|1,0.62,0.42|
|第五层|3x3|0.64,0.72|1,0.62,0.42|

## 运行方法
### keras
如果您要运行图片：
```
python infer.py  --img-path /path/to/your/img
```
如果您要在视频上跑，只需要：
```
python infer.py --img-mode 0 --video-path /path/to/video  
# 如果要打开本地摄像头, video_path填写0就可以了，如下
python infer.py --img-mode 0 --video-path 0
```
### caffe
caffe运行方法基本类似，只不过将`infer.py`换成`caffe_infer.py即可`
**注意，我们使用了permute层，所以需要使用caffe-ssd，也就是SSD作者开源的[caffe版本](https://github.com/weiliu89/caffe/tree/ssd)**，官方版本的caffe并不包含permute层。

不过如果您需要可以在官方版本的caffe上可以运行的模型，也可以联系我们修改模型，实现不需要permute层的模型。
## 附录
### 问题反馈与交流
欢迎AI圈和科技圈的朋友关注我们的公众号，这是我们分享AI技术和资讯的地方。我们要做的事情是搭建开发者和AI算法和产品需求方的一个桥梁，欢迎有AI算法需求的朋友关注我们。

![](/img/wx.png)

**如果你有任何问题，欢迎关注我们的公众号，通过后台给我留言，或者添加作者元峰的微信AIZOOTech与我联系 ，我会将您拉入AIZOO技术交流群。**

### 模型结构图
为了可视化方便，我们省略了BN层，如果您要查看完整模型，可以查看`img`文件夹的`face_mask_detection.hdf5.png`图片

![](/img/face_mask_detection.caffemodel.png)

### 测试集PR曲线
因为WIDER face是一个任务比较复杂的数据集，我们的模型又设计的非常小，所以对于人脸的PR曲线并不是那么性感。这点可以通过设计大模型来提升对于小人脸的检测效果，如果您有需求，欢迎通过上述二维码联系我们。
![](/img/pr_curve.png)

### 我们的网页长这样
欢迎大家点击链接在线体验

[aizoo.com跑在您浏览器的口罩检测模型](https://aizoo.com/face-mask-detection.html)

![](/img/face.png)









 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)