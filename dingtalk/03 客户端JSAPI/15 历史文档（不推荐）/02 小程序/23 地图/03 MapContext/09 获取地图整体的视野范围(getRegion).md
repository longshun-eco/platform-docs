---
title: "获取地图整体的视野范围(getRegion)"
source: "https://open.dingtalk.com/document/development/mapcontext-getregion"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 地图 / MapContext"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mapcontext-getregion_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mapcontext-getregion_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17使用**MapContext.getRegion**可获取地图东北角、西南角的经纬度，从而获取地图整体的视野范围。

![[development-mapcontext-getregion_p163574.png]]

**重要**

IDE 模拟器暂不支持模拟，请以真机调试效果为准。

## 示例代码

```
// .js
this.mapCtx = dd.createMapContext('map');
this.mapCtx.getRegion({
  success: res => {
    console.log(res);
  }
});
```

## **success 返回值**

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| southwest | Object | 地图的西南角经纬度。 |
| northeast | Object | 地图的东北角经纬度。 |

**返回值示例**

```json
{
  "northeast":{"latitude":39.90159974373447,"longitude":116.39376148581508},
  "southwest":{"latitude":39.89839488008665,"longitude":116.38624861836435}
}
```

## **兼容性**

使用 **dd.canIUse('createMapContext.return.****getRegion****')**进行可用性判断。