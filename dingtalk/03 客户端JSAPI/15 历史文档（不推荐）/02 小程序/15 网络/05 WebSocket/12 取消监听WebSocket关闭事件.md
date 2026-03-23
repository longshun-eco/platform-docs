---
title: "取消监听WebSocket关闭事件"
source: "https://open.dingtalk.com/document/development/dd-offsocketclose"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 网络 / WebSocket"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-offsocketclose_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-offsocketclose_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.offSocketClose**取消监听WebSocket关闭事件。

## **示例代码**

```
Page({
  onLoad() {
  dd.onSocketClose(this.callback);
  },
  onUnload() {
    dd.offSocketClose(this.callback);
    //    dd.offSocketClose();
  },
  callback(res) {
  dd.alert({content: '连接已关闭！'});
   },
})
```