---
title: "监听WebSocket错误"
source: "https://open.dingtalk.com/document/development/dd-onsocketerror"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 网络 / WebSocket"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-onsocketerror_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-onsocketerror_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.onSocketError**监听WebSocket错误。

## 示例代码

```javascript
dd.connectSocket({
  url: '开发者的服务器地址'
});

dd.onSocketOpen(function(res){
  console.log('WebSocket 连接已打开！');
});

dd.onSocketError(function(res){
  console.log('WebSocket 连接打开失败，请检查！');
});
```