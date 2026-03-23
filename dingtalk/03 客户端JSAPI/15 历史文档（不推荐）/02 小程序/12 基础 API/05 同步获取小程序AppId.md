---
title: "同步获取小程序AppId"
source: "https://open.dingtalk.com/document/development/synchronously-obtain-the-appid-of-the-mini-program"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础 API"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-synchronously-obtain-the-appid-of-the-mini-program_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-synchronously-obtain-the-appid-of-the-mini-program_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.getAppIdSync**同步获取小程序的AppId，即MiniAppId。

## 扫码体验

![[development-synchronously-obtain-the-appid-of-the-mini-program_p406823.png]]

**说明**

开发者可以通过**dd.canIUse**函数判断端上是否支持此能力。

## 示例代码

```javascript
const appIdRes = dd.getAppIdSync();
console.log(appIdRes.appId);
```

## 返回值

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| appId | String | 当前小程序的AppId，即MiniAppId。 |