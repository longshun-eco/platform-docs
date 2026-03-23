---
title: "writeBLECharacteristicValue"
source: "https://open.dingtalk.com/document/development/jsapi-write-ble-characteristic-value"
category: "客户端JSAPI / 基础API / 设备 / 蓝牙 / 低功耗蓝牙"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-write-ble-characteristic-value_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-write-ble-characteristic-value_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用writeBLECharacteristicValue，向低功耗蓝牙设备特征值中写入数据。

> * 设备的特征值必须支持 write 才可以成功调用，具体参照 characteristic 的properties 属性。
> * 写入的二进制数据需要进行 hex 编码。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10164) |

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
| deviceId | String | 是 | 0D9C82AD-1CC0-414D-9526-119E08D28124 | 蓝牙设备 ID。  * Android 上为设备 MAC 地址。 * iOS 上为设备 UUID。 |
| serviceId | String | 是 | 00001800-0000-1000-8000-00805f9b34fb | 蓝牙特征值对应 service 的 uuid。 |
| characteristicId | String | 是 | 9fa480e0-4967-4542-9390-d343dc5d04ae | 蓝牙特征值的 uuid。 |
| value | String | 是 | 0x26FF | 蓝牙设备特征值对应的值，16进制字符串，限制在20字节内。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.writeBLECharacteristicValue({
  value: '0x26FF',
  deviceId: '0D9C82AD-1CC0-414D-9526-119E08D28124',
  serviceId: '00001800-0000-1000-8000-00805f9b34fb',
  characteristicId: '9fa480e0-4967-4542-9390-d343dc5d04ae',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```