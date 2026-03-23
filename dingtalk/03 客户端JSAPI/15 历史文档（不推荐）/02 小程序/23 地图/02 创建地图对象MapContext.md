---
title: "创建地图对象MapContext"
source: "https://open.dingtalk.com/document/development/create-the-map-object-mapcontex"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 地图"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-create-the-map-object-mapcontex_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-create-the-map-object-mapcontex_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.createMapContext**创建并返回一个地图上下文对象。

创建并返回一个地图上下文对象[MapContext 概览](/document/orgapp/mapcontext-overview)。

**​**相关组件详情，请参见[map 地图](/document/orgapp/map-map)。

## **示例代码**

```
//.axml
```

## **入参**

Object 类型，属性：

|  |  |  |
| --- | --- | --- |
| **参数** | **是否必填** | **说明** |
| mapId | 是 | [map 地图](/document/orgapp/map-map)的ID。 |

## **返回值**

[MapContext](/document/orgapp/mapcontext-overview)

## **PageContext.setData(Object)**

初始化或重置地图数据，参数可选。

**示例代码**

```java
this.setData({
    scale: 14,
    longitude: 120.131441,
    latitude: 30.279383,
    'show-location':true,
    'ground-overlays':[{
        'include-points':[{// 右上
            latitude: 39.935029,
            longitude: 116.384377,
          },{// 左下
            latitude: 39.939577,
            longitude: 116.388331,
          }],
        image:'/image/groundoverlay.png',
        alpha:0.75,
        zIndex:0,
    }],
    'tile-overlay':{
      url:'http://xixi.fullspeed.cn/public/map',
      type:0,
      tileWidth:256,
```

## **错误码**

错误码信息请参见：

* [Andriod 地图错误码对照表](https://lbs.amap.com/api/android-sdk/guide/map-tools/error-code)
* [iOS 地图错误码对照](https://lbs.amap.com/api/ios-sdk/guide/map-tool/errorcode/)