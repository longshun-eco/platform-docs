---
title: "searchMap"
source: "https://open.dingtalk.com/document/development/jsapi-search-map"
category: "客户端JSAPI / 基础API / 位置"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-search-map_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-search-map_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用searchMap，唤起地图页面。

唤起地图页面，根据设备位置或者传入的经纬度搜索POI。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11674) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11674) |

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
| scope | Number | 是 | 500 | 限制搜索POI的范围；设备位置为中心，scope为搜索半径。 |
| latitude | Number | 是 | 39.903578 | 纬度。 |
| longitude | Number | 是 | 116.473565 | 经度。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| province | String | 北京市 | POI所在省会，可能为空。 |
| provinceCode | String | 11 | POI所在省会编码，可能为空。 |
| city | String | 北京市 | POI所在城市，可能为空。 |
| cityCode | String | 11 | POI所在城市编码，可能为空。 |
| adName | String | 朝阳区 | POI所在区名称，可能为空。 |
| adCode | String | 010 | POI所在区编码，可能为空。 |
| distance | String | 500 | POI与设备位置的距离。 |
| postCode | String | 100000 | POI的邮编，可能为空。 |
| snippet | String | 西大望路甲12-2号楼 | POI的街道地址，可能为空。 |
| title | String | title | POI的名称。 |
| latitude | String | 39.90357 | POI的纬度。 |
| longitude | String | 116.473565 | POI的经度。 |

## **示例****代码**

### 默认出入参

```javascript
dd.searchMap({
  scope: 500,
  latitude: 39.903578,
  longitude: 116.473565,
  success: (res) => {
    const {
      city,
      title,
      adCode,
      adName,
      snippet,
      cityCode,
      distance,
      latitude,
      postCode,
      province,
      longitude,
      provinceCode,
    } = res;
  },
  fail: () => {},
```

`success`返回对象示例：

```json
{
  "city": "北京市",
  "title": "title",
  "adCode": "010",
  "adName": "朝阳区",
  "snippet": "西大望路甲12-2号楼",
  "cityCode": "11",
  "distance": "500",
  "latitude": "39.90357",
  "postCode": "100000",
  "province": "北京市",
  "longitude": "116.473565",
  "provinceCode": "11"
}
```