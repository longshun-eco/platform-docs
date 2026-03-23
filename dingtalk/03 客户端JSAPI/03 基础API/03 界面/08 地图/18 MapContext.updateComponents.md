---
title: "MapContext.updateComponents"
source: "https://open.dingtalk.com/document/development/jsapi-map-context-update-components"
category: "客户端JSAPI / 基础API / 界面 / 地图"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-map-context-update-components_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-map-context-update-components_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

MapContext.updateComponents用于增量更新地图。

### 兼容性

使用 dd.canIUse('createMapContext.return.updateComponents') 进行可用性判断。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10136) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| scale | Number | 否 | 16 | 缩放级别，取值范围为 5-18。 默认值：16。 |
| command | Object | 是 |  | 命令，可用于更新 marker 动画。 |
| latitude | Number | 是 | 120 | 中心纬度。 |
| longitude | Number | 是 | 30.2 | 中心经度。 |
| markers | Array<Object> | 是 | [{ latitude: 39.984060, longitude: 116.307520, title: '中国技术交易大厦', address: '北京市海四环西路66号', iconPath:'/images/home\_press.png' }] | 覆盖物，在地图上的一个点绘制图标。 |
| polyline | Array<Object> | 是 | [{ points: [{ latitude: 30.264786, longitude: 120.10775 }]}] | 覆盖物，多个连贯点的集合（路线）。 |
| include-points | Array<Object> | 是 | [{ latitude: 30.279383, longitude: 120.131441 }] | 视野将进行小范围延伸包含传入的坐标。 |
| include-padding | Object | 是 |  | 视野在地图 padding 范围内展示。 |
| setting | Object | 是 |  | 设置。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```json
{"loc":{"start":{"line":4,"column":500}},"codeFrame":"  2 | \t\t\n  3 |       \tmapContext.updateComponents({\n> 4 |         scale: 16,command: {},markers: [{      latitude: 39.984060,      longitude: 116.307520,      title: '中国技术交易大厦',      address: '北京市海四环西路66号',      iconPath:'/images/home_press.png' }],setting: {showScale: '1',showCompass: '1',showMapText: '0',logoPosition: {centerX: '150',centerY: '90',},gestureEnable: '1',trafficEnabled: '0',tiltGesturesEnabled: '1',},latitude: 120,polyline: [{       points: [{         latitude: 30.264786,         longitude: 120.10775,     }], }],longitude: 30.2,include-points: [{     latitude: 30.279383,     longitude: 120.131441 }],include-padding: {top: 0,left: 0,right: 0,bottom: 0,},\n    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    ^\n  5 |       })\n  6 |       "}
```