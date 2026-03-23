---
title: "getDingerDeviceStatus"
source: "https://open.dingtalk.com/document/development/jsapi-get-dinger-device-status"
category: "客户端JSAPI / DingTalk A1"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-dinger-device-status_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-dinger-device-status_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-02-12

查询 DingTalk A1 设备状态

查询 DingTalk A1 设备状态

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 8.2.15 | 8.2.15 | 8.0.28 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11939) |
| 小程序 | 8.2.15 | 8.2.15 | 8.0.28 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11939) |

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
| deviceId | String | 否 | 123456 | 设备 id |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| device\_status | Number | 0 | 0: 没有设备；1: idle；2: 未连接 |
| audio\_status | String | idle | idle/recording/paused/streaming/rec\_streaming |
| fid | String | 12345 | 录音文件 id |
| duration | Number | 12345 | 非idle状态标识录音时长，单位毫秒 |
| battery\_percent | Number | 2 | 电量百分点：0~100 |
| storage\_total\_size | String | 0 | 总存储空间;单位MBytes |
| storage\_remain | String | 0 | 剩余存储空间;单位MBytes |
| version | String | xxx | 固件版本号 |
| accountId | String | 0 | 组织或企业id |
| occupyOperation | String | xxx | 选填，有以下操作时增加该字段，未有操作则不返回。当前设备占用情况，枚举值为： ota\_upgrading file\_syncing voiceprint\_recording |
| deviceName | String | DingTalk A1 | 设备名称 |
| bleName | String | DingTalk A1 | 蓝牙名称 |
| sn | String | xxx | 设备 sn 号 |
| deviceId | String | 12345 | 当前设备 deviceId，查询失败返回当前 deviceId |
| bleStatus | Boolean | true | 蓝牙是否连接 |
| accountType | Number | 0 | 0个人版，1企业版 |

## **示例****代码**

### 默认Demo标题

```javascript
dd.getDingerDeviceStatus({
  deviceId: '123456',
  success: (res) => {
    const {
      device_status,
      audio_status,
      fid,
      duration,
      battery_percent,
      storage_total_size,
      storage_remain,
      version,
      accountId,
      accountType,
      occupyOperation,
      deviceName,
      bleStatus,
      bleName,
      sn,
      deviceId,
    } = res;
```

`success`返回对象示例：

```json
{
  "sn": "xxx",
  "fid": "12345",
  "bleName": "DingTalk A1",
  "version": "xxx",
  "deviceId": "12345",
  "duration": 12345,
  "accountId": "0",
  "bleStatus": true,
  "deviceName": "DingTalk A1",
  "accountType": 0,
  "audio_status": "idle",
  "device_status": 0,
  "storage_remain": "0",
  "battery_percent": 2,
  "occupyOperation": "xxx",
  "storage_total_size": "0"
}
```