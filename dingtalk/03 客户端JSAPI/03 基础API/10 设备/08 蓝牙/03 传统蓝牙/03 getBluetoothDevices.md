---
title: "getBluetoothDevices"
source: "https://open.dingtalk.com/document/development/jsapi-get-bluetooth-devices"
category: "客户端JSAPI / 基础API / 设备 / 蓝牙 / 传统蓝牙"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-bluetooth-devices_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-bluetooth-devices_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用getBluetoothDevices，获取所有已发现的蓝牙设备，包括已经和本机处于连接状态的设备。

> * 模拟器可能无法获取advertisData及RSSI，请使用真机调试。
> * 开发者工具和Android上获取到的deviceId为设备MAC地址，iOS上则为设备uuid。因此deviceId 不能硬编码到代码中，需要分平台处理，iOS可根据设备属性（ localName、advertisData、manufacturerData等属性）进行动态匹配。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10178) |

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

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| devices | Array<Object> |  |  |

## **示例****代码**

### 默认出入参

```javascript
dd.getBluetoothDevices({
  success: (res) => {
    const { devices } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "devices": [
    {
      "RSSI": 100,
      "name": "我的耳机",
      "deviceId": "0D9C82AD-1CC0-414D-9526-119E08D28124",
      "localName": "名称",
      "deviceName": "我的耳机",
      "advertisData": "0x26FF",
      "manufacturerData": "0x1800"
    }
  ]
}
```