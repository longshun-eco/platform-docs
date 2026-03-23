---
title: "getWifiHotspotStatus"
source: "https://open.dingtalk.com/document/development/jsapi-get-wifi-hotspot-status"
category: "客户端JSAPI / 基础API / 设备 / 网络状态"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-wifi-hotspot-status_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-wifi-hotspot-status_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用getWifiHotspotStatus，获取热点接入信息。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11665) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11665) |

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

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| ssid | String | alibaba-inc | 热点ssid。 |
| macIp | String | 3c:12:aa:09 | 热点mac地址。 |

## **示例****代码**

### 默认出入参

```javascript
dd.getWifiHotspotStatus({
  success: (res) => {
    const { ssid, macIp } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "ssid": "alibaba-inc", "macIp": "3c:12:aa:09" }
```