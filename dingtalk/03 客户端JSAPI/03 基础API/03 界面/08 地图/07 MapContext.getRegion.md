---
title: "MapContext.getRegion"
source: "https://open.dingtalk.com/document/development/jsapi-map-context-get-region"
category: "客户端JSAPI / 基础API / 界面 / 地图"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-map-context-get-region_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-map-context-get-region_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

使用MapContext.getRegion可获取地图东北角、西南角的经纬度，从而获取地图整体的视野范围。

![[development-jsapi-map-context-get-region_p163574.png]]

### 重要

IDE 模拟器暂不支持模拟，请以真机调试效果为准。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10128) |

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
| northeast | Object |  | 地图的东北角经纬度。 |
| southwest | Object |  | 地图的西南角经纬度。 |

## **示例****代码**

### 默认出入参

```javascript
const mapContext = dd.createMapContext();

mapContext.getRegion({
  success: (res) => {
    const { northeast, southwest } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "northeast": {
    "latitude": 39.89839488008665,
    "longitude": 116.38624861836435
  },
  "southwest": {
    "latitude": 39.90159974373447,
    "longitude": 116.39376148581508
  }
}
```