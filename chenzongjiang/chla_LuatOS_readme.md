     

[![license](https://img.shields.io/github/license/openLuat/LuatOS)](/LICENSE)
[![rtt-w60x ci](https://github.com/openLuat/LuatOS/workflows/rtt-w60x/badge.svg)](https://github.com/openLuat/LuatOS/actions?query=workflow%3Artt-w60x)
[![qemu ci](https://github.com/openLuat/LuatOS/workflows/qemu-vexpress-a9/badge.svg)](https://github.com/openLuat/LuatOS/actions?query=workflow%3Aqemu-vexpress-a9)
[![stm32f103re ci](https://github.com/openLuat/LuatOS/workflows/stm32f103re/badge.svg)](https://github.com/openLuat/LuatOS/actions?query=workflow%3Astm32f103re)
[![issue](https://img.shields.io/github/issues/openLuat/LuatOS)](https://github.com/openLuat/LuatOS/issues)

LuatOS是运行在嵌入式硬件的实时操作系统,只需要少量内存的flash空间就能运行,用户编写lua代码就可完成各种功能

Lua base RTOS, build for many embedded systems

1. 基于Lua 5.3.5
2. 低内存需求, 最低32kb, 96kb flash空间
3. 硬件抽象层兼容M3/arm/risc-v等
4. 可测试,可模拟(qemu)
5. 在线升级
6. 可裁剪,可扩展

**QQ群: 1061642968**

[LuatOS@码云](https://gitee.com/openLuat/LuatOS)

[LuatOS@github](https://github.com/openLuat/LuatOS)

----------------------------------------------------------------------------------
## 总体架构

![总体架构](system.jpg)

## 代码示例节选

详细代码请查阅 [script/app/playit/main.lua](script/app/playit/main.lua)

```lua
local sys = require("sys")
local httpv2 = require("httpv2")

sys.subscribe("WLAN_READY", function ()
    print("!!! wlan ready event !!!")
    -- 马上进行时间同步
    socket.ntpSync()
end)

disp.init("ssd1306")
display_str("Booting ...")

-- 配网回调
sys.subscribe("WLAN_PW_RE", function(ssid, password)
    if ssid then
        log.info(TAG, "airkiss GOT", ssid, password)
        local conf = {ssid=ssid,password=password}
        json.encodeFile(conf, "/wlan.json")
    else
        log.info(TAG, "airkiss fail")
    end
end)

-- 业务流程, 联网后定时发送温度数据到服务器
sys.taskInit(function()
    while 1 do
        if wlan.ready() then
            sys.wait(1000)
            local temp = (sensor.ds18b20(28) or "")
            local code,headers,body = httpv2.request("GET", "http://site0.cn/api/w60x/report/ds18b20?mac=" .. wlan.get_mac() .. "&temp=" .. tostring(temp))
            display_str("Temp: " .. temp  .. " rssi:" .. tostring(wlan.rssi()))
            log.info("network", "http complete, sleep 5s", code, body)
            sys.wait(5000)
        else
            log.warn("main", "wlan is not ready yet")
            sys.waitUntil("WLAN_READY", 30000)
        end
    end
end)

-- 主循环, 必须加
sys.run()
```

----------------------------------------------------------------------------------
## 资源

* 参阅 [Luat 平台层](docs/markdown/core/luat_platform.md)
* [文档索引](docs.md)
* [搭建开发环境](docs/markdown/proj/workspace.md)
* [如何开发](docs/markdown/proj/how_to_dev.md)
* [预编译固件](https://github.com/openLuat/LuatOS/releases)
* [Lua 5.3中文手册](https://www.runoob.com/manual/lua53doc/)
* [合宙官网](http://www.openluat.com)
* [合宙商城](http://m.openluat.com)
* [联盛德W600/合宙Air640W专属说明](docs/markdown/bsp/w600.md)
* [合宙Air302专属说明](bsp/air302/README.md)

----------------------------------------------------------------------------------
## 配套

TODO: 构建工具链,IDE,刷机工具,等等

## 使用到的开源项目

* [rt-thread](https://github.com/RT-Thread/rt-thread) 国产rtos, 非常好用
* [rtt-ds18b20](https://github.com/willianchanlovegithub/ds18b20) 在RT-Thread环境下读取ds18b20
* [LuaTask](https://github.com/openLuat/Luat_2G_RDA_8955) 合宙LuaTask
* [iRTU](https://github.com/hotdll/iRTU) 基于Luat的DTU, 稀饭大神
* [airkissOpen](https://github.com/heyuanjie87/airkissOpen) 参考其实现思路

## 授权协议

[MIT License](LICENSE)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)