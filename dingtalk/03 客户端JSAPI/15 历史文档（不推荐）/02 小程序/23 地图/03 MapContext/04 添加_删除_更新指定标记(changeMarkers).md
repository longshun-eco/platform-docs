---
title: "添加/删除/更新指定标记(changeMarkers)"
source: "https://open.dingtalk.com/document/development/mapcontext-changemarkers"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 地图 / MapContext"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mapcontext-changemarkers_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mapcontext-changemarkers_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17使用**MapContext.changeMarkers**用于添加、删除、更新指定的标记（marker）。

## **示例代码**

```
// .js
this.mapCtx = dd.createMapContext('map');
this.mapCtx.changeMarkers({
  add:[{
      iconPath: "/image/green_tri.png",
      id: 10,
      latitude: 30.279383,
      longitude: 120.131441,
      width: 50,
      height: 50
    },{
      iconPath: "/image/green_tri.png",
      id: 10,
      latitude: 30.279383,
      longitude: 120.131441,
      width: 50,
      height: 50,
      customCallout: {
        type: 1,
        time: '1',
      },
```

## **入参**

| **参数** | 类型 | 说明 |
| --- | --- | --- |
| add | Array | 需要添加的 marker 数组。 |
| remove | Array | 需要删除的 marker 数组。 |
| update | Array | 需要更新的 marker 数组。 |

## **兼容性**

使用 **dd.canIUse('createMapContext.return.changeMarkers')**进行可用性判断。