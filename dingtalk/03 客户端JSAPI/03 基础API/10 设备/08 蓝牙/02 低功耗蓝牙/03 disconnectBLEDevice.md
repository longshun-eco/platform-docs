---
title: "disconnectBLEDevice"
source: "https://open.dingtalk.com/document/development/jsapi-disconnect-bledevice"
category: "客户端JSAPI / 基础API / 设备 / 蓝牙 / 低功耗蓝牙"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-disconnect-bledevice_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-disconnect-bledevice_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用disconnectBLEDevice，断开与低功耗蓝牙设备的连接。

> * 蓝牙连接随时可能断开，建议监听 `onBLEConnectionStateChanged` 回调事件，当蓝牙设备断开时按需执行重连操作。
> * 若对未连接的设备或已断开连接的设备调用数据读写操作的接口，会返回10006错误，详见错误码，建议进行重连操作。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10163) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| deviceId | String | 是 | 0D9C82AD-1CC0-414D-9526-119E08D28124 | 蓝牙设备ID。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.disconnectBLEDevice({
  deviceId: '0D9C82AD-1CC0-414D-9526-119E08D28124',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```