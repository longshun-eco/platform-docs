---
title: "关闭WebSocket连接"
source: "https://open.dingtalk.com/document/development/dd-closesocket"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 网络 / WebSocket"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-closesocket_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-closesocket_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.closeSocket**关闭WebSocket连接。

## **示例****代码**

```javascript
dd.onSocketOpen(function() {
  dd.closeSocket()
})

dd.onSocketClose(function(res) {
  console.log('WebSocket 已关闭！')
})
```

## **入参说明**

| **参数** | **类型** | **是否必填** | **说明** |
| --- | --- | --- | --- |
| success | Function | 否 | 回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Function | 否 | 调用结束的回调函数（调用成功、失败都会执行）。 |