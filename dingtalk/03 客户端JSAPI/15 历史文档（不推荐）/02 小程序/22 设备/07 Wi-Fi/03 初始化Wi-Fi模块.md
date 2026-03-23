---
title: "初始化Wi-Fi模块"
source: "https://open.dingtalk.com/document/development/initialize-the-wi-fi-module"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 设备 / Wi-Fi"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-initialize-the-wi-fi-module_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-initialize-the-wi-fi-module_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用 **startWifi**，初始化 Wi-Fi 模块。

## **使用说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **客户端** | **Android** | **iOS** | **PC** |
| 支持说明 | 支持(钉钉版本≥7.0.10) | 支持(钉钉版本≥7.0.10) | 不支持 |

## **示例代码**

```javascript
dd.startWifi({
  success: function(res) {
    console.log(res)
  }
})
```

## **入参说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **参数** | **类型** | **是否必填** | **描述** |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Funciton | 否 | 调用结束的回调。  **说明**  调用成功、失败都会执行。 |