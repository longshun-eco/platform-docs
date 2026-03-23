---
title: "监听WebSocket关闭"
source: "https://open.dingtalk.com/document/development/dd-onsocketclose"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 网络 / WebSocket"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-onsocketclose_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-onsocketclose_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.onSocketClose**监听WebSocket关闭。

## **示例****代码**

```java
onLoad() {
    // 注意： 回调方法的注册在整个小程序启动阶段只要做一次，调多次会有多次回调
    dd.onSocketClose((res) => {
      dd.alert({content: '连接已关闭！'});
      this.setData({
        sendMessageAbility: false,
        closeLinkAbility: false,
      });
    });
    // 注意： 回调方法的注册在整个小程序启动阶段只要做一次，调多次会有多次回调
    dd.onSocketOpen((res) => {
      dd.alert({content: '连接已打开！'});
      this.setData({
        sendMessageAbility: true,
        closeLinkAbility: true,
      });
    });

    dd.onSocketError(function(res){
      dd.alert('WebSocket 连接打开失败，请检查！' + res);
    });
```