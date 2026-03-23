---
title: "MapContext.calculateDistance"
source: "https://open.dingtalk.com/document/development/jsapi-map-context-calculate-distance"
category: "客户端JSAPI / 基础API / 界面 / 地图"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-map-context-calculate-distance_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-map-context-calculate-distance_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

MapContext.calculateDistance提供地图路径计算能力，用于计算途径地图上多个点的总路线距离。也可根据该路线截取部分子路线，加上其他目标点的路径规划后，组合成新的路径。

传入一组点（例如 points 数组 [A,B,C]），计算经过这些点的总路径长度。也可传入目标距离，返回目标坐标点 B'，目标坐标点 B'与 points 数组中第一个点 A 的直线距离，等于目标距离。假设 B'- A 直线距离在 B-A 直线距离、C-A 直线距离之间，则返回 points 数组中的点 B 的索引数值。 例如传入的 points 数组为本市所有川菜外卖店，传入目标距离为 3 km，则可返回距离当前地点 3 km 内，离我最远的川菜外卖店的索引值。

### 兼容性

使用 dd.canIUse('createMapContext.return.calculateDistance') 进行可用性判断。

### 重要

IDE 模拟器暂不支持模拟，请以真机调试效果为准。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10122) |

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
| points | Array<Object> | 是 | [{ latitude: 30.261775, longitude: 120.102507, },{ latitude: 30.262794, longitude: 120.103816, },{ latitude: 30.264036, longitude: 120.10491, },{ latitude: 30.265194, longitude: 120.10609, },{ latitude: 30.265824, longitude: 120.107217, },{ latitude: 30.267446, longitude: 120.109749, },{ latitude: 30.268715, longitude: 120.112721, } ] | 路线中点的经纬度数组。 |
| targetDistances | Array<Number> | 是 | [100,200,300,600] | 目标距离（直线距离）数组。 |
| exportTotalDistance | Boolean | 是 | false | 是否需要计算总距离。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| distance | Number | 0 | 总路径长度。 如果传入的 exportTotalDistance 为 false，则不返回 distance。 |
| targetPoints | Array<Object> | [{"index":0,"latitude":30.261775,"longitude":120.102507,"targetDistance":100,"targetLineIndex":0}, {"index":1,"latitude":30.261775,"longitude":120.102507,"targetDistance":200,"targetLineIndex":0}, {"index":2,"latitude":30.261775,"longitude":120.102507,"targetDistance":300,"targetLineIndex":0}, {"index":3,"latitude":30.261775,"longitude":120.102507,"targetDistance":600,"targetLineIndex":0}] | 符合目标距离的点，对应的经纬度。具体属性值参见下方 targetPoints 对象表。 |

## **示例****代码**

### 默认出入参

```javascript
const mapContext = dd.createMapContext();

mapContext.calculateDistance({
  points: [
    { latitude: 30.261775, longitude: 120.102507 },
    { latitude: 30.262794, longitude: 120.103816 },
    { latitude: 30.264036, longitude: 120.10491 },
    { latitude: 30.265194, longitude: 120.10609 },
    { latitude: 30.265824, longitude: 120.107217 },
    { latitude: 30.267446, longitude: 120.109749 },
    { latitude: 30.268715, longitude: 120.112721 },
  ],
  targetDistances: [100, 200, 300, 600],
  exportTotalDistance: false,
  success: (res) => {
    const { distance, targetPoints } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```
{
  "distance": 0,
  "targetPoints": [
    {
      "index": 0,
      "latitude": 30.261775,
      "longitude": 120.102507,
      "targetDistance": 100,
      "targetLineIndex": 0
    },
    {
      "index": 1,
      "latitude": 30.261775,
      "longitude": 120.102507,
      "targetDistance": 200,
      "targetLineIndex": 0
    },
    {
      "index": 2,
      "latitude": 30.261775,
      "longitude": 120.102507,
```