# Tensorflow-lite Deeplab RealTime 

## 1. Demo
![](http://www.ibbwhat.com/optimize1.gif)
![](http://www.ibbwhat.com/optimize2.gif)

## 2. Requirements:
- [Apple Developer Program Account](https://opencv.org/releases.html) (Simulator doesn’t have a camera)
- [Xcode 9.2](https://developer.apple.com/xcode/)
- [OpenCV 3.3.1 iOS Pack](https://opencv.org/releases.html)
- [Git LFS](https://git-lfs.github.com/)
- [Tensorflow-lite](https://www.tensorflow.org/lite/)
- any iOS device with a decent camera


## 3. Code reference

- Opencv 
  Example application made for [this post](https://medium.com/@dwayneforde/image-recognition-on-ios-with-swift-and-opencv-b5cf0667b79).

- Tensorflow 
  Example application made for [this post](https://www.tensorflow.org/lite/models/segmentation/overview)

- Model File: 
  DeepLab segmentation [download](https://storage.googleapis.com/download.tensorflow.org/models/tflite/gpu/deeplabv3_257_mv_gpu.tflite)
  (image segmentation model that assigns semantic labels (e.g., dog, cat, car) to every pixel in the input image)

## 4. Installation:
```
git clone https://github.com/toniz/deeplab-on-ios.git
cd deeplab-on-ios/
pod install
open DeeplabOnIOS.xcworkspace
```


*   DeepLabv3+:
```
@inproceedings{deeplabv3plus2018,
  title={Encoder-Decoder with Atrous Separable Convolution for Semantic Image Segmentation},
  author={Liang-Chieh Chen and Yukun Zhu and George Papandreou and Florian Schroff and Hartwig Adam},
  booktitle={ECCV},
  year={2018}
}
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)