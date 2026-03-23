---
title: "openLocation"
source: "https://open.dingtalk.com/document/development/jsapi-open-location"
category: "客户端JSAPI / 基础API / 位置"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-open-location_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-open-location_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用openLocation，使用内置地图查看位置。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10257) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10257) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

在H5应用中，调用[dd.config](https://open.dingtalk.com/document/orgapp/jsapi-authentication)完成鉴权后使用

在小程序应用中，无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| title | String | 是 | 北京国家广告产业园 | 在地图锚点气泡显示的文案。 |
| address | String | 是 | 学院路77号 | 位置描述。 |
| latitude | String | 是 | 39.903578 | 纬度，范围为 -90~90，负数表示南纬。 |
| longitude | String | 是 | 116.473565 | 经度，范围为 -180~180，负数表示西经。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.openLocation({
  title: '北京国家广告产业园',
  address: '学院路77号',
  latitude: '120.126293',
  longitude: '30.274653',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```