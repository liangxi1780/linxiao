# Aquila

English | [简体中文](README.cn.md)

[![Build](https://travis-ci.org/gozfree/aquila.svg?branch=master)](https://travis-ci.org/gozfree/aquila)
[![Release](https://img.shields.io/github/release/gozfree/aquila.svg)](https://github.com/gozfree/aquila/releases)
[![License](https://img.shields.io/github/license/gozfree/aquila.svg)](https://github.com/gozfree/aquila/blob/master/LICENSE.MIT)

Aquila is an app-level framework to process multimedia, aims to unify the
different middleware SDK on generic level. It mainly support software encoding
and decoding on CPU, and easily porting. It can be used on video surveillance,
ipcam.

## Framework
* `algo`     algorithm
* `codec`    video enc/dec codecs
* `device`   video, audio and other multimedia source devices
* `playback` video, audio and other multimedia sink devices
* `protocol` network protocols
* `util`     utility

* filter : contain media_param

## Libraries
This app is mostly based on [gear-lib](https://github.com/gozfree/gear-lib)

## Build
How to build aquila, please refer to INSTALL.md.

## Moral
Wiki: Aquila is the Latin and Romance languages word for eagle.
Meaning fast, robust, intelligent, and good eyesight.

## License
Please refer to the LICENSE file for detailed information.

## Framework

```
device ==> encode ==> decode ==> network ==> playback
v4l2       x264       h264       rtsp        sdl
fake       mjpeg                 rtmp
                                 rpc/mqtt
```


## Author & Contributing
Welcome pull request to the project.  
gozfree  


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)