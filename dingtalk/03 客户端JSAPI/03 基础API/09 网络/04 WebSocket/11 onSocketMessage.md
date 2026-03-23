---
title: "onSocketMessage"
source: "https://open.dingtalk.com/document/development/jsapi-on-socket-message"
category: "客户端JSAPI / 基础API / 网络 / WebSocket"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-on-socket-message_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-on-socket-message_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用onSocketMessage，监听WebSocket接收到服务器的消息事件。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10289) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| data | String | abc | 服务器返回的消息。  普通的文本String或者经base64编码后的String。 |
| isBuffer | Boolean | false | * true：data字段表示接收到的经过了base64编码后的String， * false：data字段表示接收到的普通String文本。 |

## **示例****代码**

### 默认出入参

```javascript
dd.onSocketMessage((res) => {
  const { data, isBuffer } = res;
});
```

返回对象示例：

```json
{ "data": "abc", "isBuffer": false }
```