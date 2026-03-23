---
title: "移动视野到定位点(moveToLocation)"
source: "https://open.dingtalk.com/document/development/mapcontext-movetolocation"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 地图 / MapContext"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mapcontext-movetolocation_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mapcontext-movetolocation_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17使用**MapContext.moveToLocation**将视野移动到定位点并恢复到默认缩放级别，需要配合map组件(audience=isv) map组件(audience=org) 的 show-location 使用。

## **示例代码**

```
this.mapCtx = dd.createMapContext('map');
this.mapCtx.moveToLocation();
```

## **兼容性**

使用 **dd.canIUse('createMapContext')** 进行可用性判断。