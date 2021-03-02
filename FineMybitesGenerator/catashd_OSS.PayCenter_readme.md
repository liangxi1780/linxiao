# 快速了解
	OSS支付SDK，主要打造微信支付，支付宝支付，以及其他银行支付接口标准库项目
	此项目以标准库的形式提供服务，也就是可以同时支持.Net Framework(4.6及以上版本) 和 .Net Core
如果有问题，也可以在公众号(osscoder)中提问:

![osscoder](http://7xil4i.com1.z0.glb.clouddn.com/osscoder_icon.jpg)

# OSS.PayCenter 使用
### 一. 安装使用
      nuget下安装命令：**Install-Package OSS.PaySdk.Wx**	（微信支付
      nuget下安装命令：**Install-Package OSS.PaySdk.Ali**	（支付宝支付

### 二. 调用示例

1. 微信调用示例：

```csharp
// 声明配置
private static WxPayCenterConfig config= new WxPayCenterConfig()
{
    AppSource = "11",
    AppId = "wx2428e34e0e7dc6ef",
    MchId = "1233410002",
    Key = "e10adc3849ba56abbe56e056f20f883e",
    AppSecret = "51c56b886b5be869567dd389b3e5d1d6",

    CertPassword = "1233410002",
    CertPath = "cert/apiclient_cert.p12",
    NotifyUrl = "http://www.osscoder.com",
    // 设置证书附加请求方式
    SetCertificata = (handler, cert) =>
    {
        handler.ServerCertificateCustomValidationCallback = (msg, c, chain, sslErrors) => true;
        handler.ClientCertificates.Add(cert);
    }
};
//  调用示例
private static WxPayTradeApi m_Api=new WxPayTradeApi(config);

public void AddUniOrderAsyncTest()
{
    var order = new WxAddPayUniOrderReq();

    order.device_info = "WEB";
    order.body = "测试商品支付";
    order.openid = "sdfvsfdbf345678888fhngfbsdfbsdfb";

    order.out_trade_no = "2017022423560123";
    order.trade_type = "JSAPI";
    order.total_fee = 100;

    var res = m_Api.AddUniOrderAsync(order).WaitResult();
    Assert.IsTrue(res.IsSuccess);
}
```

2. 支付宝调用示例

```csharp
 private static string privateKey = "自定义私钥";
 private static string publicKey = "支付宝提供的公钥";

protected static ZPayCenterConfig ZPayConfig { get; set; } = new ZPayCenterConfig()
{
    AppSource = "1",
    AppId = "2016080300153582",
    AppPrivateKey = privateKey,
    AppPublicKey = publicKey
};

protected static ZPayTradeApi zPayApi = new ZPayTradeApi(ZPayConfig);

public async Task  ZPay(PayOrderMo order)
{
    string orderNum = DateTime.Now.ToString("yyyyMMddHHmmss");

    var payReq = new ZAddPreTradeReq("http://pay.sample.osscoder.com/base/ZCallBack");

    payReq.body = order.order_name;
    payReq.out_trade_no = orderNum;
    payReq.total_amount = order.order_price;
    payReq.subject = order.order_name;

    var res =await zPayApi.AddPreTradeAsync(payReq);
    return Json(res);
}
```

### 三. 注意事项
	
	因为底层接口使用了Task返回，在.Net Framework MVC项目中如果你的在action中通过 Result或者wait等方式，直接返回ActionResult对象，界面会出现假死状态，解决方案：
	1. action 返回类型 ActionResult 修改为 async Task , 全程异步
	2. 将异步调用方法 通过 var task=  Task.Run(()=> 异步方法 )返回异步对象，再使用task.Result即可

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)