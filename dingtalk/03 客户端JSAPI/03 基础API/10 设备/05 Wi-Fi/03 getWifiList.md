---
title: "getWifiList"
source: "https://open.dingtalk.com/document/development/jsapi-get-wifi-list"
category: "客户端JSAPI / 基础API / 设备 / Wi-Fi"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-wifi-list_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-wifi-list_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

获取 Wi-Fi 列表。

在 [onGetWifiList](https://open.dingtalk.com/document/orgapp/jsapi-onGetWifiList) 注册的回调中返回 wifiList 数据。iOS 将跳转到系统设置中的钉钉设置页，需要用户手动进入「无线局域网」设置页，Android 不会跳转。

> * iOS 11.0 及 iOS 11.1 两个版本因系统问题，该方法失效。
> * 需在 [startWifi](https://open.dingtalk.com/document/orgapp/jsapi-startWifi) 中使用。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 7.0.0 | 7.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11472) |

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

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **错误码**

| **错误码** | **描述** |
| --- | --- |
| 3 | 系统异常 |

## **示例****代码**

### 默认出入参

```
dd.getWifiList({
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```