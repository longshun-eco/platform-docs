---
title: "测试回调URL事件"
source: "https://open.dingtalk.com/document/development/event-subscription-callback-test-url-event"
category: "事件订阅 / 历史文档（不推荐） / HTTP回调 / 通用回调事件"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-event-subscription-callback-test-url-event_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-event-subscription-callback-test-url-event_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-12-08在调用注册回调事件接口时，钉钉服务器会向你设置的回调URL发起POST请求，用来检测URL的合法性。本文介绍钉钉推送给你的数据格式，以及你需要返回给钉钉的数据的格式。

**说明**

测试回调URL事件适用于企业内部应用和第三方企业应用。

## 数据格式说明

在您注册事件回调接口的时候，钉钉服务器会向您“注册回调接口”时候设置的url(接收回调的url)发起POST请求，用来测试url的合法性。收到消息后，需要返回经过加密后的字符串“success”的json数据，否则钉钉服务器将认为url不合法。

**POST数据解密后示例：**

```json
{
    "EventType" : "check_url"
}
```

**返回给钉钉的数据说明：**

```json
{
  "msg_signature":"111108bb8e6dbce3c9671d6fdb69d150xxxx",
  "timeStamp":"1783610513",
  "nonce":"w2WPvWxxxxGOmIB",
  "encrypt":"1ojQf0NSvw2WPvWxxxxGOmIBNbWetRg7IP0vdhxxxx"
  }
```

**参数说明：**

|  |  |
| --- | --- |
| 参数 | 说明 |
| msg\_signature | 消息体签名。 |
| timeStamp | 时间戳。 |
| nonce | 随机字符串。 |
| encrypt | 字符串success加密值。 |