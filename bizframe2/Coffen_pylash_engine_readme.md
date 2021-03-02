# Pylash Engine
---------------

[**English**](https://github.com/yuehaowang/pylash_engine/blob/master/README.md)
|
[**中文**](https://github.com/yuehaowang/pylash_engine/blob/master/README_chs.md)

**Latest Version: 1.4.1**

`Pylash` is a game engine for `python` which imitates some classes and functions in `flash`. We develop `pylash` with `Python3` and the GUI engine of `pylash` is `PyQt4`. Many classes which are almost from `flash` such as `Sprite`, `BitmapData`, `Bitmap`, `TextField`, `Loader` and `Graphics` will be found in `pylash`.


## License: MIT License

We use [MIT License](http://en.wikipedia.org/wiki/MIT_License), which is a free and friendly license. Besides, you must follow the license of `PyQt4` as well, because `pylash` is based on it.


## Get Pylash

**With Git:**

Input this command in `Git Bash` to clone `pylash`:

```
git clone git@github.com:yuehaowang/pylash_engine.git
```

**Without Git:**

The url to download the engine is: 

[https://github.com/yuehaowang/pylash_engine/archive/master.zip](https://github.com/yuehaowang/pylash_engine/archive/master.zip)


## Before Using Pylash

For `pylash` is based on `Python3` and `PyQt4`, you need to install them first.

**Python3 will be found here:**

[https://www.python.org/](https://www.python.org/)

**PyQt4 will be found here:**

[https://riverbankcomputing.com/software/pyqt/intro](https://riverbankcomputing.com/software/pyqt/intro)


## Support

If you find the library has some bugs or that you have any questions or advice, please let us know:

> **My email:** wangyuehao1999@gmail.com
> 
> **My twitter:** [https://twitter.com/yuehaowang](https://twitter.com/yuehaowang)

Bugs can be submited into [Github Issues](https://github.com/yuehaowang/pylash_engine/issues) too.


## Demo Screenshots

- **Find Character**

![Demo 1](http://images.cnblogs.com/cnblogs_com/yorhom/731449/o_pylash_demo1.png)

- **Get Fruits**

![Demo 2](http://images.cnblogs.com/cnblogs_com/yorhom/731449/o_pylash_demo2.png)

- **Tower Defense**

![Demo 3](http://images.cnblogs.com/cnblogs_com/yorhom/731449/o_pylash_demo3.png)


## Get Started

- [Overview of Pylash](https://github.com/yuehaowang/pylash_engine/wiki/Overview-of-Pylash)
- [A Simple Program: Hello World](https://github.com/yuehaowang/pylash_engine/wiki/A-Simple-Program:-Hello-World)
- [Load and Display An Image](https://github.com/yuehaowang/pylash_engine/wiki/Load-and-Display-An-Image)
- [Sprite and Mouse Event](https://github.com/yuehaowang/pylash_engine/wiki/Sprite-and-Mouse-Event)
- [Create Vector Graphics](https://github.com/yuehaowang/pylash_engine/wiki/Create-Vector-Graphics)


## Documentation

Documentation comes soon...


## Changelog

### version 1.4.1

*Release Date: 3/13/2016*

1. Added `globalToLocal` method in `DisplayObject` class to get a point's position which is relative to the global coordinate.
2. Added `localToGlobal` method in `DisplayObject` class to get a point's position which is relative to the local coordinate of display object.
3. Added `Matrix` class in `geom` module to create a matrix used for transforming coordinate.
4. Added `Transform` class in `geom` module and `transform` property in `DisplayObject`. With them, you can transform display object arbitrarily.

### version 1.4.0

*Release Date: 2/7/2016*

1. Enhancement: you can set `width`&`height` property of `DisplayObject` to limit the size of display object.
2. Added `Sound` class in `media` module to play music.
3. Enhancement: using `LoadManage.load`, you can load music.
4. Improvement: `LoadManage` used to use `threading.thread` to create a thread, now it use `QThread`.

### version 1.3.3

*Release Date: 1/10/2016*

1. Added `LineEdit` class in `ui` module to create single-line input box.
2. Added `RankingSystem` in `system` module, which connect server and send requests to add/get ranking.
3. Added `RankingServer` in `net` module, which is a `socket` server used with `RankingSystem`.
4. Bugfix: cannot use `onComplete`&`onStart`&`onUpdate` property in `TweenLite`.

### version 1.3.2

*Release Date: 12/26/2015*

1. Added `ButtonSample` in `ui` module, which is used for creating a very simple button. Generally speaking, it's used for testing.
2. Added `StageWebView` in `media` module to show some webpages in the window.

### version 1.3.1

*Release Date: 11/21/2015*

1. Added `draw` method in `BitmapData` to draw a display object in `BitmapData` object.
2. Improvement: change drawing `QImage` object into drawing `QPixmap` object to make image rendering fast.
3. Added `setPixel`, `getPixel`, `setPixels`, `getPixels` method in `BitmapData` for pixel processing.
4. Added `lock`, `unlock` method in `BitmapData` for faster pixel processing when you process pixels many times at a time.
5. Added `Rectangle` class and `Point` class.
6. Bugfix: get wrong width/height of `Graphics` when using `moveTo` method or `lineTo` method.
7. Enhancement: support hex value when setting color.

### version 1.3.0

*Release Date: 11/8/2015*

1. Bugfix: some errors will be thrown when you give a `LinearGradientColor`/`RadialGradientColor`/`ConicalGradientColor` object to `lineStyle` method of `Graphics` class as the second parameter.
2. Added `TweenLite` static class and `TweenLiteChild` class to create some easing animations.
3. Added `Easing` static class to provide many easing methods for `TweenLite` class.
4. Improvement: more detailed internal error hints.
5. Bugfix: cannot use `Button.removeState`.

#### version 1.2.1

*Release Date: 11/1/2015*

1. Added `Shape` class to create vector graphics. It's lighter than `Sprite` when you just want to use vector graphics.
2. Enhancement: efficiency of mouse event.

#### version 1.2.0

*Release Date: 10/7/2015*

1. Added some sample classes about loading page.
2. Added `Button` class to create a simple button.
3. Added `LinearGradientColor`, `RadialGradientColor` and `ConicalGradientColor` class to use gradient color.
4. Added `delay` property in `LoadManage` class to set the delay time between loading a resource and loading the next resource in order to show loading page.
5. Added `useAntialiasing` property in `stage` in order to open/close antialiasing.
6. Bugfix: `onComplete` callback function will be called in the thread used for loading resources in `LoadManage`.
7. Bugfix: `PyQt` will throw errors if `text` property of `TextField` is set to a value whose type is not `str`.
8. Added `mouseShelter` property in `DisplayObjectContainer` to set whether stop propagating mouse events to `DisplayObjectContainer` objects that are sheltered by other objects.
9. Bugfix: `selfY` in mouse event is wrong.
10. Enhancement: the `x` and `y` property in parameter 'bitmapData' given into the constructor of `Animation` class will be the origin position of the animation.
11. Added `AnimationSet` class to control a set of animations.
12. Added `MOUSE_OVER` and `MOUSE_OUT` event.

#### version 1.1.0

*Release Date: 9/20/2015*

1. Improvement: changed and added some methods in `Graphics`.
2. Added settings of `join style`, `cap style` and `miter limit` in `Graphics`.

#### version 1.0.0 

*Release Date: 9/12/2015*

Create `pylash` with `display`, `text`, `system`, `utils` and `events` modules which include `Sprite`, `Bitmap`, `Graphics`, `Loader`, `Stage` and more powerful classes.

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)