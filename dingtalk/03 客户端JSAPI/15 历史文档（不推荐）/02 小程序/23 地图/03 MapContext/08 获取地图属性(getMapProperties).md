---
title: "获取地图属性(getMapProperties)"
source: "https://open.dingtalk.com/document/development/mapcontext-getmapproperties"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 地图 / MapContext"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mapcontext-getmapproperties_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mapcontext-getmapproperties_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17使用**MapContext.getMapProperties**获取地图的属性信息。

## **使用限制**

钉钉客户端版本号为5.1.2及以后的版本。

## **出参**

| **参数** | **类型** | **说明** |
| --- | --- | --- |
| is3d | Boolean | 是否是 3D 地图引擎。  更多信息可参见：[高德开放平台-3D 地图](https://lbs.amap.com/api/javascript-api/guide/map/3d-map/?sug_index=0)。 |
| isSupportAnim | Boolean | 是否支持动画。 |
| sdkName | String | 地图中使用的 SDK 名称。  更多信息可参见 ：   * [高德地图 Android SDK简介](https://lbs.amap.com/api/android-sdk/summary/) * [高德地图 iOS SDK简介](https://lbs.amap.com/api/ios-sdk/summary) |
| sdkVersion | String | 地图中使用的 SDK 版本号。  更多信息可参见 ：   * [高德地图 Android SDK简介](https://lbs.amap.com/api/android-sdk/summary/) * [高德地图 iOS SDK简介](https://lbs.amap.com/api/ios-sdk/summary) |
| isSupportOversea | Boolean | 是否支持海外地图。 |
| needStyleV7 | Boolean | 是否需要 7.x 版本自定义地图样式配置文件。  更多信息可参见 ：   * [高德地图 Android 自定义地图](https://lbs.amap.com/api/android-sdk/guide/create-map/custom/?sug_index=2) * [高德地图 iOS 自定义地图](https://lbs.amap.com/api/ios-sdk/guide/create-map/custom/?sug_index=1) |

## **兼容性**

使用 **dd.canIUse('createMapContext.return.****getMapProperties****')**进行可用性判断