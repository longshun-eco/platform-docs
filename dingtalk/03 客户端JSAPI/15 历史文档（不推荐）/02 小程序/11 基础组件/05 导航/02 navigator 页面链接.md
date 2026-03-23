---
title: "navigator 页面链接"
source: "https://open.dingtalk.com/document/development/mini-app-navigator-page-link-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 导航"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-navigator-page-link-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-navigator-page-link-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍页面链接组件的使用。

**扫码体验**

![[development-mini-app-navigator-page-link-1_p170201.png]]

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| hover-class | String | 点击时附加的类。  **默认值**：none。 |
| hover-start-time | Number | 按住多长时间后出现点击状态，单位毫秒。 |
| hover-stay-time | Number | 手指松开后点击状态保留时间，单位毫秒。 |
| url | String | 应用内的跳转链接。 |
| open-type | String | 跳转方式。  **默认值**：navigate。 |

open-type 有效值：

| **属性** | **描述** |
| --- | --- |
| navigate | 对应 dd.navigateTo 的功能。 |
| redirect | 对应 dd.redirectTo 的功能。 |
| switchTab | 对应 dd.switchTab 的功能。 |
| navigateBack | 对应 dd.navigateBack 的功能。 |

## 示例代码

.axm示例代码：

```
  导航栏
  跳转到新页面
  在当前页打开
  跳转到另外一个 Tab - "组件"
  reLaunch
  navigateBack
```

.acss示例代码：

```
navigator {
  background-color:  lightcoral;
  color:  #fff;
  margin-bottom: 10rpx;
  padding: 20rpx;
  text-align: center;
}

.navigator-hover {
  background-color:  lightskyblue;
  color:  #fff;
}
```