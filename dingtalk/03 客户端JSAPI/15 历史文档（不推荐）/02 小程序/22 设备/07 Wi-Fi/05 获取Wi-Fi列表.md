---
title: "获取Wi-Fi列表"
source: "https://open.dingtalk.com/document/development/get-wi-fi-list"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 设备 / Wi-Fi"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-get-wi-fi-list_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-get-wi-fi-list_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用 **getWifiList**，获取 Wi-Fi 列表。

## **功能描述**

在 [onGetWifiList](https://open.dingtalk.com/document/orgapp/listener-to-get-wi-fi-list-event) 注册的回调中返回 wifiList 数据。iOS 将跳转到系统设置中的钉钉设置页，需要用户手动进入「无线局域网」设置页，Android 不会跳转。

## **使用说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **客户端** | **Android** | **iOS** | **PC** |
| 支持说明 | 支持(钉钉版本≥7.0.10) | 支持(钉钉版本≥7.0.10) | 不支持 |

**说明**

* iOS 11.0 及 iOS 11.1 两个版本因系统问题，该方法失效。
* 需在 [startWifi](/document/orgapp/initialize-the-wi-fi-module) 中使用。

## **示例代码**

```
dd.getWifiList();
```

## **入参说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **参数** | **类型** | **是否必填** | **描述** |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Funciton | 否 | 调用结束的回调。  **说明**  调用成功、失败都会执行。 |