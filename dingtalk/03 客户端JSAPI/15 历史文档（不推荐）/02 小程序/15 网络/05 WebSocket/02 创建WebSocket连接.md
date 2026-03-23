---
title: "创建WebSocket连接"
source: "https://open.dingtalk.com/document/development/dd-connectsocket"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 网络 / WebSocket"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-connectsocket_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-connectsocket_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.connectSocket**创建一个 WebSocket 的连接。

**重要**

一个钉钉小程序同时只能保留一个 WebSocket 连接，如果当前已存在 WebSocket 连接，会自动关闭该连接，并重新创建一个新的 WebSocket 连接。

## **示例****代码**

```
dd.connectSocket({
  url: 'test.php',
  data: {},
  header:{
    'content-type': 'application/json'
  },
  method:"GET",
});
```

## **入参**

| **参数** | **类型** | **是否必填** | **说明** |
| --- | --- | --- | --- |
| url | String | 是 | 目标服务器url。 |
| data | Object | 否 | 请求的参数。 |
| header | Object | 否 | 设置请求的头部。 |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Function | 否 | 调用结束的回调函数（调用成功、失败都会执行）。 |

## **错误码**

| **error** | **描述** |
| --- | --- |
| 1 | 未知错误。 |
| 2 | 网络连接已经存在。 |
| 3 | URL参数为空。 |
| 4 | 无法识别的URL格式。 |
| 5 | URL必须以ws或者wss开头。 |
| 6 | 连接服务器超时。 |
| 7 | 服务器返回的https证书无效。 |
| 8 | 服务端返回协议头无效。 |
| 9 | WebSocket请求没有指定Sec-WebSocket-Protocol请求头。 |
| 10 | 网络连接没有打开，无法发送消息。 |
| 11 | 消息发送失败。 |
| 12 | 无法申请更多内存来读取网络数据。 |