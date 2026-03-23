---
title: "getBLEDeviceServices"
source: "https://open.dingtalk.com/document/development/jsapi-get-ble-device-services"
category: "客户端JSAPI / 基础API / 设备 / 蓝牙 / 低功耗蓝牙"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-ble-device-services_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-ble-device-services_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用getBLEDeviceServices，获取蓝牙设备所有服务。

> 建立连接后先执行`getBLEDeviceServices`与`getBLEDeviceCharacteristics`后再进行与蓝牙设备的数据交互。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10167) |

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
| deviceId | String | 是 | 0D9C82AD-1CC0-414D-9526-119E08D28124 | 蓝牙设备 id。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| services | Array<Object> |  |  |

## **示例****代码**

### 默认出入参

```javascript
dd.getBLEDeviceServices({
  deviceId: '0D9C82AD-1CC0-414D-9526-119E08D28124',
  success: (res) => {
    const { services } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "services": [
    { "isPrimary": true, "serviceId": "00001800-0000-1000-8000-00805f9b34fb" }
  ]
}
```