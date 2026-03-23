---
title: "MapContext.getMapProperties"
source: "https://open.dingtalk.com/document/development/jsapi-map-context-get-map-properties"
category: "客户端JSAPI / 基础API / 界面 / 地图"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-map-context-get-map-properties_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-map-context-get-map-properties_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

使用MapContext.getMapProperties获取地图的属性信息。

### 兼容性

使用 dd.canIUse('createMapContext.return.getMapProperties')进行可用性判断

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10127) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| is3d | Boolean | true | 是否是 3D 地图引擎。  更多信息可参见：[高德开放平台-3D 地图。](https://lbs.amap.com/api/javascript-api/guide/map/3d-map/?spm=ding_open_doc.document.0.0.11d21e7bDQP5PA&sug_index=0) |
| sdkName | String |  | 地图中使用的 SDK 名称。  更多信息可参见 ：   * [高德地图 Android SDK简介](https://lbs.amap.com/api/android-sdk/summary/?spm=ding_open_doc.document.0.0.11d21e7bDQP5PA) * [高德地图 iOS SDK简介](https://lbs.amap.com/api/ios-sdk/summary?spm=ding_open_doc.document.0.0.11d21e7bDQP5PA) |
| sdkVersion | String | 8.0.0 | 地图中使用的 SDK 版本号。  更多信息可参见 ：   * [高德地图 Android SDK简介](https://lbs.amap.com/api/android-sdk/summary/) * [高德地图 iOS SDK简介](https://lbs.amap.com/api/ios-sdk/summary) |
| needStyleV7 | Boolean | true | 是否需要 7.x 版本自定义地图样式配置文件。  更多信息可参见 ：   * [高德地图 Android 自定义地图](https://lbs.amap.com/api/android-sdk/guide/create-map/custom/?spm=ding_open_doc.document.0.0.11d21e7bDQP5PA&sug_index=2) * [高德地图 iOS 自定义地图](https://lbs.amap.com/api/ios-sdk/guide/create-map/custom/?spm=ding_open_doc.document.0.0.11d21e7bDQP5PA&sug_index=1) |
| isSupportAnim | Boolean | true | 是否支持动画。 |
| isSupportOversea | Boolean | true | 是否支持海外地图。 |

## **示例****代码**

### 默认出入参

```javascript
const mapContext = dd.createMapContext();

mapContext.getMapProperties();
```

返回对象示例：

```json
{
  "is3d": true,
  "sdkName": `sdkName示例值`,
  "sdkVersion": "8.0.0",
  "needStyleV7": true,
  "isSupportAnim": true,
  "isSupportOversea": true
}
```