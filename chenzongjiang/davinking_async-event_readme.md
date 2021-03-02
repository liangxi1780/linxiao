# async-event
进程内部异步事件调用组件

## 解决什么问题：

+   加速服务处理效率。提供进程级别的事件发布和异步处理能力。
+   服务解耦。观察者和发布者之间互不干涉，解耦关系。
+   事件驱动。提供一对多的对象关系。
+   最终一致性。低延时，最终一致。


## 生产数据：

+   使用异步事件组件优化服务[前]：
+   tps->2000,tp90->100ms,tp99->120ms
+   使用异步事件组件优化服务[后]：
+   tps->2000,tp90->20ms,tp99->30ms  

## 总体设计

![总体设计](/doc/frame.png)


## Usage:

        //实例化事件总线，使用内存队列
        final EventBus eventBus = new EventBus(new MemoryChannel(1024));
        //注册消费者
        eventBus.register(new ListenerSub());
        eventBus.register(new BothSub());
        //启动事件总线
        eventBus.start();

        //发送事件消息（需要启动后才能发送）
        eventBus.publish(new SimpleEvent());
        eventBus.publish(new EventAny());
        eventBus.publish(new EventA());
        //停止事件总线
        eventBus.stop();

## 开发计划


        1、持久化增加mybatis.
        2、远程storage服务，统一管理。统一组件化。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)