---
title: "连接Wi-Fi"
source: "https://open.dingtalk.com/document/development/connection-wi-fi"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 设备 / Wi-Fi"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-connection-wi-fi_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-connection-wi-fi_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用 **connectWifi**，连接 Wi-Fi。

## **功能描述**

若已知 Wi-Fi 信息，可以直接利用该接口连接。

## **使用说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **客户端** | **Android** | **iOS** | **PC** |
| 支持说明 | 支持(钉钉版本≥7.0.10) | 支持(钉钉版本≥7.0.10) | 不支持 |

**说明**

仅 Android 与 iOS 11 以上版本支持。

## **示例代码**

```javascript
my.connectWifi({
  SSID: '',
  BSSID: '',
  success: function(res) {
    console.log(res)
  }
})
```

## **入参说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **参数** | **类型** | **是否必填** | **描述** |
| SSID | String | 是 | Wi-Fi 设备的 SSID。 |
| BSSID | String | 否 | Wi-Fi 设备的 BSSID。 |
| password | String | 否 | Wi-Fi 设备密码。 |
| isWEP | Boolean | 否 | Wi-Fi 是否为 WEP。  **说明**  默认是 false。 |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Funciton | 否 | 调用结束的回调。  **说明**  调用成功、失败都会执行。 |