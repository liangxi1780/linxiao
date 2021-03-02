 

# Electronic WeChat

*A better WeChat on macOS and Linux. Built with [Electron](https://github.com/atom/electron).*

> **⚠️⚠️ NO LONGER IN ACTIVE DEVELOPMENT | 项目不再维护 ⚠️⚠️** 
> 
> Thanks for supporting this project for **1000** days since Feb 16, 2016. 
> 
> It started with the idea to make WeChat better on MacOS when the official support was abscent. It was de facto dead when Tencent rolled out a new WeChat and started to block other third-party clients. For me, it's no longer worthwhile to hack a lot to accomplish little. Hope this project had been helpful to you in any way. You're welcome to fork or make copies with a reference. HAPPY HACKING.
>
> 感谢历史上的用户和贡献者，你们已经陪伴这个项目走过了 **1000** 个日子。我曾经想要打造一个更好的 Mac 微信客户端，因为官方版本几年没有更新、bug 层出。而在腾讯自己开始了定期更新并限制第三方客户端时，这个项目实际已经没有什么意义。这个项目目前作为一个存档供大家学习。希望它曾经对你有所帮助，你也可以 fork 或者转载（标注来源）来进行修改。祝你玩得愉快。
>
> **SPECIAL THANKS TO | 特别感谢**
> 
> [Kulbear](https://github.com/Kulbear), 
> [arrowrowe](https://github.com/arrowrowe), 
> [Rocka](https://github.com/rocka), 
> [CC](https://github.com/iamcc), 
> [xgdgsc](https://github.com/xgdgsc), 
> [死水微澜](https://github.com/ripples-alive), 
> [Jason](https://github.com/gzzhanghao), 
> [Ce Gao](https://github.com/gaocegege), 
> [viko16](https://github.com/viko16), 
> [卡晨](https://github.com/awmleer), 
> [Ray](https://github.com/ray26), 
> [尹良灿](https://github.com/wenLiangcan), 
> [gehuangyi20](https://github.com/gehuangyi20), 
> [Kevin Tan](https://github.com/stkevintan), 
> [Jiaye Wu](https://github.com/wujysh), 
> [loufq](https://github.com/loufq), 
> [Miaow](https://github.com/miaowing), 
> [Chuan Ji](https://github.com/jichu4n), 
> [Oaker](https://github.com/cyio), 
> [Fengshuang Li](https://github.com/lfs1102), 
> [Song Li](https://github.com/boltomli), 
> [afon](https://github.com/samurai00), 
> [lional wang](https://github.com/3dseals), 
> [Haochen Tong](https://github.com/hexchain), 
> [Zhuoyun Wei](https://github.com/wzyboy), 
> [rivershang](https://github.com/rivershang), 
> [Ivan Jiang](https://github.com/iplus26), 
> [oBlank](https://github.com/oblank), 
> [Cheng Gu](https://github.com/gucheen), 
> [NullMDR](https://github.com/NullMDR), 
> [ReadmeCritic](https://github.com/ReadmeCritic).
---

**Important:** If you want to build the app by yourself rather than download the release directly, please consider to use the source code from [the production branch](https://github.com/geeeeeeeeek/electronic-wechat/tree/production), the master branch is under development and we cannot guarantee it to be stable.

[![Gitter](https://badges.gitter.im/geeeeeeeeek/electronic-wechat.svg)](https://gitter.im/geeeeeeeeek/electronic-wechat?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=body_badge)
[![Build Status](https://travis-ci.org/geeeeeeeeek/electronic-wechat.svg?branch=master)](https://travis-ci.org/geeeeeeeeek/electronic-wechat)
[![Build Status](https://img.shields.io/github/stars/geeeeeeeeek/electronic-wechat.svg)](https://github.com/geeeeeeeeek/electronic-wechat)
[![Build Status](https://img.shields.io/github/forks/geeeeeeeeek/electronic-wechat.svg)](https://github.com/geeeeeeeeek/electronic-wechat)
[![Build Status](https://img.shields.io/badge/README-切换语言-yellow.svg)](README_zh.md)

![qq20160428-0 2x](https://cloud.githubusercontent.com/assets/7262715/14876747/ff691ade-0d49-11e6-8435-cb1fac91b3c2.png)

## Features ([CHANGELOG](CHANGELOG.md))

- **Modern UI and all features from Web WeChat.**
- **Block message recall.**
- **Stickers showing support.** [[?]](https://github.com/geeeeeeeeek/electronic-wechat/issues/2)
- Share subscribed passages on Weibo, Qzone, Facebook, Twitter, Evernote, and email.
- Mention users in a group chat.
- Drag and drop to send photos.
- Behaves like a native app, based on dozens of optimization.
- Removes URL link redirects and takes you directly to blocked websites (e.g. taobao.com).

## How To Use

To clone and run this repository you'll need [Git](https://git-scm.com) and [Node.js](https://nodejs.org/en/download/) (which comes with [npm](https://www.npmjs.com/)) installed on your computer. From your command line:

``` bash
# Clone this repository
git clone https://github.com/geeeeeeeeek/electronic-wechat.git
# Go into the repository
cd electronic-wechat
# Install dependencies and run the app
npm install && npm start
```

To pack into an app, simply type one of these:

``` shell
npm run build:osx
npm run build:linux
npm run build:win32
npm run build:win64
```

**New:** Install with your familiar package manager. Check out [images maintained by the community](https://github.com/geeeeeeeeek/electronic-wechat/wiki/System-Support-Matrix#%E7%A4%BE%E5%8C%BA%E8%B4%A1%E7%8C%AE%E7%9A%84%E5%AE%89%E8%A3%85%E5%8C%85)!

**New:** Or, with homebrew!

```bash
brew cask install electronic-wechat
```

#### [Download Released App](https://github.com/geeeeeeeeek/electronic-wechat/releases)

#### License [MIT](LICENSE.md)

*Electronic WeChat* is released by this open source project. While Web WeChat is a major component  in the app, it should be noted that this is a community release and not an official WeChat release.


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)