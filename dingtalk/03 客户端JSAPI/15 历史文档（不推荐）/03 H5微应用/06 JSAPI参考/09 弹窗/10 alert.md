---
title: "alert"
source: "https://open.dingtalk.com/document/development/alert"
category: "客户端JSAPI / 历史文档（不推荐） / H5微应用 / JSAPI参考 / 弹窗"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-alert_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-alert_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**device.notification.alert**显示警告框，可以设置警告框的标题、内容、按钮文字等。

## 调试

访问[JSAPI Explorer](https://open-dev.dingtalk.com/apiExplorer#/jsapi?api=device.notification.alert)在线调试该接口。

## 使用说明

| **客户端** | **Android** | **iOS** | **PC** |
| --- | --- | --- | --- |
| 支持说明 | 支持 | 支持 | 支持 |

```javascript
dd.device.notification.alert({
    message: "测试",
    title: "提示",//可传空
    buttonName: "收到",
    onSuccess : function() {
        //onSuccess将在点击button之后回调
        /*回调*/
    },
    onFail : function(err) {}
});
```

## 参数说明

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| message | String | 消息内容。 |
| title | String | 弹窗标题。 |
| buttonName | String | 按钮名称。 |