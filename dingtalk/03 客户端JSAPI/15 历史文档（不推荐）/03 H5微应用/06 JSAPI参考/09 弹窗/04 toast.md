---
title: "toast"
source: "https://open.dingtalk.com/document/development/toast"
category: "客户端JSAPI / 历史文档（不推荐） / H5微应用 / JSAPI参考 / 弹窗"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-toast_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-toast_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**device.notification.toast**实现toast弹窗。

## 调试

访问[JSAPI Explorer](https://open-dev.dingtalk.com/apiExplorer#/jsapi?api=device.notification.toast)在线调试该接口。

## 使用说明

| **客户端** | **Android** | **iOS** | **PC** |
| --- | --- | --- | --- |
| 支持说明 | 支持 | 支持 | 支持(参数不同，icon) |

```javascript
dd.device.notification.toast({
    icon: '', //icon样式，不同客户端参数不同，请参考参数说明
    text: String, //提示信息
    duration: Number, //显示持续时间，单位秒，默认按系统规范[android只有两种(<=2s >2s)]
    delay: Number, //延迟显示，单位秒，默认0
    onSuccess : function(result) {
        /*{}*/
    },
    onFail : function(err) {}
})
```

## 参数说明

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| icon | String | icon样式，不同客户端参数不同：   * Android和iOS样式：success和error，默认为空 * PC端样式：alert，success，error，warning，information，confirm，默认information |
| text | String | 必填，提示信息。 |
| duration | Number | 显示持续时间，单位秒，默认按系统规范。  Android只有两种(<=2s和>2s)。 |
| delay | Number | 延迟显示，单位秒，默认0。 |