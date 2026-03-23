---
title: "onBluetoothDeviceFound"
source: "https://open.dingtalk.com/document/development/jsapi-on-bluetooth-device-found"
category: "客户端JSAPI / 基础API / 设备 / 蓝牙 / 传统蓝牙"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-on-bluetooth-device-found_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-on-bluetooth-device-found_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用onBluetoothDeviceFound，搜索到新的蓝牙设备时触发此事件。

> * 模拟器可能无法获取 advertisData 及 RSSI ，请使用真机调试。
> * 开发者工具和 Android 上获取到的deviceId为设备 MAC 地址，iOS 上则为设备 uuid。因此deviceId不能硬编码到代码中，需要分平台处理，iOS可根据设备属性（localName/advertisData/manufacturerData等）进行动态匹配。
> * 若在onBluetoothDeviceFound 回调中包含了某个蓝牙设备，则此设备会添加到getBluetoothDevices接口获取到的数组中。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10180) |

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
| RSSI | Number | 100 | 设备信号强度。 |
| name | String | 我的耳机 | 蓝牙设备名称，某些设备可能没有。 |
| deviceName | String | 我的耳机 | 值与 name 一致。兼容旧版本。 |
| localName | String | 名称 | 广播设备名称。 |
| deviceId | String | 0D9C82AD-1CC0-414D-9526-119E08D28124 | 设备 Id。 |
| advertisData | String | 0x26FF | 设备的广播内容。 |

## **示例****代码**

### 默认出入参

```javascript
dd.onBluetoothDeviceFound((res) => {
  const { RSSI, name, deviceId, localName, deviceName, advertisData } = res;
});
```

返回对象示例：

```json
{
  "RSSI": 100,
  "name": "我的耳机",
  "deviceId": "0D9C82AD-1CC0-414D-9526-119E08D28124",
  "localName": "名称",
  "deviceName": "我的耳机",
  "advertisData": "0x26FF"
}
```