---
title: "计算地图路径(calculateDistance)"
source: "https://open.dingtalk.com/document/development/mapcontext-calculatedistance"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 地图 / MapContext"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mapcontext-calculatedistance_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mapcontext-calculatedistance_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17**MapContext.calculateDistance**提供地图路径计算能力，用于计算途径地图上多个点的总路线距离。也可根据该路线截取部分子路线，加上其他目标点的路径规划后，组合成新的路径。

传入一组点（例如 points 数组 [A,B,C]），计算经过这些点的总路径长度。也可传入目标距离，返回目标坐标点 B'，目标坐标点 B'与 points 数组中第一个点 A 的直线距离，等于目标距离。假设 B'- A 直线距离在 B-A 直线距离、C-A 直线距离之间，则返回 points 数组中的点 B 的索引数值。

例如传入的 points 数组为本市所有川菜外卖店，传入目标距离为 3 km，则可返回距离当前地点 3 km 内，离我最远的川菜外卖店的索引值。

**重要**

IDE 模拟器暂不支持模拟，请以真机调试效果为准。

## **示例代码**

```javascript
// .js
const aniPoints = [{
      latitude: 30.261775,
      longitude: 120.102507,
    },{
      latitude: 30.262794,
      longitude: 120.103816,
    },{
      latitude: 30.264036,
      longitude: 120.10491,
    },{
      latitude: 30.265194,
      longitude: 120.10609,
    },{
      latitude: 30.265824,
      longitude: 120.107217,
    },{
      latitude: 30.267446,
      longitude: 120.109749,
    },{
      latitude: 30.268715,
```

## **返回值示例代码**

```json
{"distance":0,"success":true,"targetPoints":
  [{"index":0,"latitude":30.261775,"longitude":120.102507,"targetDistance":100,"targetLineIndex":0},

  {"index":1,"latitude":30.261775,"longitude":120.102507,"targetDistance":200,"targetLineIndex":0},

  {"index":2,"latitude":30.261775,"longitude":120.102507,"targetDistance":300,"targetLineIndex":0},

  {"index":3,"latitude":30.261775,"longitude":120.102507,"targetDistance":600,"targetLineIndex":0}]
}
```

## **入参**

| **参数** | **类型** | **是否必填** | **说明** |
| --- | --- | --- | --- |
| points | Array | 是 | 路线中点的经纬度数组。 |
| exportTotalDistance | Boolean | 否 | 是否需要计算总距离。  **默认值**： true。 |
| targetDistances | Array | 否 | 目标距离（直线距离）数组。 |

**success 返回值**

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| distance | Number | 总路径长度。  如果传入的 exportTotalDistance 为 false，则不返回 distance。 |
| targetPoints | Array | 符合目标距离的点，对应的经纬度。具体属性值参见下方 targetPoints 对象表。 |

**targetPoints 对象**

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| index | Number | 与 points 数组中首个点的直线距离符合目标距离的点，在 targetDistances 中的索引。 |
| targetDistance | Array | 目标距离的数值。（如果不传 targetPoints 或 targetPoints 参数为空，则返回的 targetDistances字段也为空）。 |
| latitude | Number | 纬度。 |
| longitude | Number | 经度。 |
| targetLineIndex | Number | 假设 points 数组为 [A,B,C]，符合目标距离的点为 B'， 且 B'- A 直线距离在 B-A 直线距离、C-A 直线距离之间，则 targetLineIndex 为 points 数组中的点 B 的索引数值。 |

## **兼容性**

使用 **dd.canIUse('createMapContext.return.calculateDistance')** 进行可用性判断。