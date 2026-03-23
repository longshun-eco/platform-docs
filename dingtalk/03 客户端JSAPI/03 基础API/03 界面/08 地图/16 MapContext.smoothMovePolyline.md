---
title: "MapContext.smoothMovePolyline"
source: "https://open.dingtalk.com/document/development/jsapi-map-context-smooth-move-polyline"
category: "客户端JSAPI / 基础API / 界面 / 地图"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-map-context-smooth-move-polyline_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-map-context-smooth-move-polyline_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

MapContext.smoothMovePolyline用于轨迹动画。

### 兼容性

使用 dd.canIUse('createMapContext.return.smoothMovePolyline') 进行可用性判断。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10134) |

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
| polylineId | Number | 是 | o | 执行动画的路线 ID。 |
| points | Array<Object> | 是 | [{ latitude: 30.261775, longitude: 120.102507, },{ latitude: 30.262794, longitude: 120.103816, },{ latitude: 30.264036, longitude: 120.10491, },{ latitude: 30.265194, longitude: 120.10609, },{ latitude: 30.265824, longitude: 120.107217, },{ latitude: 30.267446, longitude: 120.109749, },{ latitude: 30.268715, longitude: 120.112721, } ] | 动画路线的经纬度集合。 |
| duration | Number | 否 | 500 | 动画执行时间。 默认值：5000 毫秒（ms）。 |
| color | String | 否 | #FF00DD | 轨迹动画的颜色。 |
| width | Number | 否 | 10 | 路线宽度。 |
| dottedLine | Boolean | 否 | false | 是否虚线。 |
| iconPath | String | 否 | /image/map\_alr.png | 线的纹理地址。 |
| iconWidth | Number | 否 | 10 | 线的纹理宽度。 |
| zIndex | Number | 否 | 4 | 线的 Z 轴坐标。 |
| colorList | Array<String> | 否 | ["#FF00DD", "#FFFFFF"] | 彩虹线。 |
| action | String | 否 |  | 指定操作动画。   * action:'stop'表示提前结束动画。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```javascript
const mapContext = dd.createContext();

mapContext.smoothMovePolyline({
  color: '#FF0000D',
  width: 1,
  action: `action示例值`,
  points: [
    { latitude: 30.261775, longitude: 120.102507 },
    { latitude: 30.262794, longitude: 120.103816 },
    { latitude: 30.264036, longitude: 120.10491 },
    { latitude: 30.265194, longitude: 120.10609 },
    { latitude: 30.265824, longitude: 120.107217 },
    { latitude: 30.267446, longitude: 120.109749 },
    { latitude: 30.268715, longitude: 120.112721 },
  ],
  zIndex: 4,
  duration: 500,
  iconPath: '/image/map_alr.png',
  colorList: [],
  iconWidth: 10,
  dottedLine: false,
```