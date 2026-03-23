---
title: "信任SSID"
source: "https://open.dingtalk.com/document/development/trust-ssid"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 设备 / Wi-Fi"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-trust-ssid_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-trust-ssid_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用 **registerSSID**，信任该 SSID。

## **功能描述**

信任该 SSID，对于需要 Portal 认证的 Wi-Fi，不会弹出 Portal 认证页面。

## **使用说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **客户端** | **Android** | **iOS** | **PC** |
| 支持说明 | 不支持 | 支持(钉钉版本≥7.0.10) | 不支持 |

## **示例代码**

```javascript
dd.registerSSID({
  SSID: 'SSID示例值',
  success: (res) => {
    const {} = res;
  },
  fail: () => {},
  complete: () => {},
});
```

## **入参说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **参数** | **类型** | **是否必填** | **描述** |
| SSID | String | 是 | 设备 SSID。 |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Funciton | 否 | 调用结束的回调。  **说明**  调用成功、失败都会执行。 |