---
title: "打开iOS系统设置"
source: "https://open.dingtalk.com/document/development/open-ios-system-settings"
category: "客户端JSAPI / 历史文档（不推荐） / H5微应用 / JSAPI参考 / 设备"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-open-ios-system-settings_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-open-ios-system-settings_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**device.base.openSystemSetting**打开iOS系统设置页面。

## 使用说明

| 客户端 | Android | iOS | PC | **是否需鉴权** |
| --- | --- | --- | --- | --- |
| 支持说明 | 不支持 | 支持（钉钉版本≥6.3.15） | 不支持 | 否 |

```javascript
dd.device.base.openSystemSetting({
    onSuccess : function() {
    },
    onFail : function() {
    }
})
```

## 参数说明

| 参数 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| onSuccess | Function | 否 | 调用成功的回调函数。 |
| onFail | Function | 否 | 调用失败的回调函数。 |