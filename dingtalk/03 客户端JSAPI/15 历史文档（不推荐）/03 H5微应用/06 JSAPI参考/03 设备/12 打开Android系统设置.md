---
title: "打开Android系统设置"
source: "https://open.dingtalk.com/document/development/open-android-system-settings"
category: "客户端JSAPI / 历史文档（不推荐） / H5微应用 / JSAPI参考 / 设备"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-open-android-system-settings_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-open-android-system-settings_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**device.base.openSystemSetting**打开系统设置。

## 使用说明

| 客户端 | Android | iOS | PC | **是否需鉴权** |
| --- | --- | --- | --- | --- |
| 支持说明 | 支持（钉钉版本≥4.6.36） | 不支持 | 不支持 | 否 |

```javascript
dd.device.base.openSystemSetting({
    action: "android.settings.BLUETOOTH_SETTINGS",
    param: "extended data",
    data: "data param",
    onSuccess : function() {
    },
    onFail : function() {
    }
})
```

## 参数说明

| 参数 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| action | String | 是 | Android系统中action的概念。  例如：**android.settings.BLUETOOTH\_SETTINGS**：打开蓝牙设置页面  更多action参考[详情](https://developer.android.com/reference/android/provider/Settings)。 |
| param | Json | 否 | Android系统中跳转系统应用所需的**extra**参数。 |
| data | String | 否 | Android系统中跳转系统应用所需的**data**参数。 |
| onSuccess | Function | 否 | 调用成功的回调函数。 |
| onFail | Function | 否 | 调用失败的回调函数。 |

## 返回结果

| 参数 | 说明 |
| --- | --- |
| 3 | 未知错误 |