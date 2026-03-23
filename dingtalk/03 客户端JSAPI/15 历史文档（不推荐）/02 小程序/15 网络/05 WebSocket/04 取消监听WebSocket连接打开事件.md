---
title: "取消监听WebSocket连接打开事件"
source: "https://open.dingtalk.com/document/development/dd-offsocketopen"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 网络 / WebSocket"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-offsocketopen_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-offsocketopen_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.offSocketOpen**取消监听WebSocket连接打开事件。

## **示例****代码**

```
Page({
  onLoad() {
    this.callback = this.callback.bind(this);
    dd.onSocketOpen(this.callback);
  },
  onUnload() {
    dd.offSocketOpen(this.callback);
  },
  callback(res) {
  },
})
```