---
title: "sendSocketMessage"
source: "https://open.dingtalk.com/document/development/jsapi-send-socket-message"
category: "客户端JSAPI / 基础API / 网络 / WebSocket"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-send-socket-message_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-send-socket-message_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用sendSocketMessage，通过WebSocket连接发送数据；需要先使用connectSocket发起连接，再使用onSocketOpen回调之后再发送数据。

需要先使用connectSocket发起连接，再使用onSocketOpen收到连接打开回调之后再发送数据。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10288) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| data | String | 是 | abc | 需要发送的内容。  普通的文本内容String或者经base64编码后的String。 |
| isBuffer | Boolean | 否 | true | 如果需要发送二进制数据，需要将入参数据经base64编码成String后赋值data，同时将此字段设置为true，否则如果是普通的文本内容String，不需要设置此字段。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.sendSocketMessage({
  data: 'abc',
  isBuffer: false,
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```