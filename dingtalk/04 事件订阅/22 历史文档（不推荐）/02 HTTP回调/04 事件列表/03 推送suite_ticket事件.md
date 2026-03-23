---
title: "推送suite_ticket事件"
source: "https://open.dingtalk.com/document/development/push-suite-ticket-events"
category: "事件订阅 / 历史文档（不推荐） / HTTP回调 / 事件列表"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-push-suite-ticket-events_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-push-suite-ticket-events_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-16钉钉开放平台会向应用的回调URL不定期（约5个小时）推送suite\_ticket事件。

应用在收到suite\_ticket推送后务必返回经过加密的字符串"success"的json数据。如果不返回，钉钉服务器将连续推送，直到推送次数超过100次，就不再推送。

**说明**

开发者需要持久化suite\_ticket，不要设置失效的缓存时间，新的ticket推送会使之前的ticket失效，推送suite\_ticket事件适用于第三方企业应用。

倘若您希望钉钉服务器重新推送，进入[开发者后台](https://open-dev.dingtalk.com/)，点击您创建的应用，在**开发管理**页面单击**重新推送**。

![[development-push-suite-ticket-events_p258816.png]]

**POST数据解密后示例：**

```json
{
  "SuiteKey": "xxxxxx",
  "EventType": "suite_ticket",
  "TimeStamp": 123456,
  "SuiteTicket": "xxxxxx"
}
```

**参数说明：**

| 参数 | 说明 |
| --- | --- |
| SuiteKey | 应用的SuiteKey。 |
| EventType | 回调事件类型。 |
| TimeStamp | 时间戳。 |
| SuiteTicket | ticket内容。 |

应用在收到此事件推送后务必返回包含经过加密的字符串"success"的JSON数据。只有返回了对应的JSON数据，钉钉才会判断此事件推送成功。

```json
{
  "msg_signature":"111108bb8e6dbce3c9671d6fdb69d15066227608",
  "timeStamp":"1783610513",
  "nonce":"123456",
  "encrypt":"1vn9lYTuuHSoaxwCGylH9xRhasdfghjkl" // "success"字段的加密数据
}
```

其中：

* **msg\_signature**：消息体签名。
* **timeStamp**：时间戳。
* **nonce**：随机字符串。
* **encrypt**："success"的加密字符串。