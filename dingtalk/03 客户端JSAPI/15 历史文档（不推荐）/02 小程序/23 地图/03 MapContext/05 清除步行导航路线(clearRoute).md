---
title: "清除步行导航路线(clearRoute)"
source: "https://open.dingtalk.com/document/development/mapcontext-clearroute"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 地图 / MapContext"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mapcontext-clearroute_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mapcontext-clearroute_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17使用**MapContext.clearRoute**清除地图上的步行导航路线。

## **示例代码**

```
this.mapCtx = dd.createMapContext('map');
this.mapCtx.clearRoute();
```

## **兼容性**

使用 **dd.canIUse('createMapContext.return.clearRoute')**进行可用性判断。