---
title: "视频会议ASR转写结果开放事件"
source: "https://open.dingtalk.com/document/development/events-meeting-asr-result-event"
category: "事件订阅 / 音视频 / 视频/音频会议"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-events-meeting-asr-result-event_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-events-meeting-asr-result-event_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

## 事件信息

|  |  |
| --- | --- |
| 名称 | 值 |
| 中文名称 | 视频会议ASR转写结果开放事件 |
| 英文名称 | meeting\_asr\_result\_event |

## 功能描述

会议中的闪记ASR转写识别结果事件。

## 支持应用类型

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | Stream模式推送 | HTTP推送 | SyncHTTP/RDS推送 |
| 企业内部应用 | 支持 | 支持 | 不支持 |
| 第三方企业应用 | 支持 | 不支持 | 支持 |

## 事件体描述

Stream模式推送

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| eventUnifiedAppId | String | bbb381b6-f01xxxxx58daac | 统一应用身份Id。 |
| eventCorpId | String | ding9f50b15bxxxx16741 | 事件所属的corpId。 |
| eventType | String | meeting\_asr\_result\_event | 事件类型。 |
| eventId | String | c7c7120f2c07419\*\*ebdba0318c8 | 事件的唯一Id。 |
| eventBornTime | Long | 1683533823336 | 事件生成时间。 |
| data | Object |  | 事件体data。 |

### **事件体示例**

```
{
```

HTTP推送

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| EventType | String | meeting\_asr\_result\_event | 事件英文名称。 |
| EventTime | Long | 1663143335567 | 事件发生的时间。 |
| CorpId | String | ding9f50b15bxxxx16741 | 企业corpId。 |
| BizId | String | 1663\*\*35567 | 无业务意义，幂等。 |
| eventId | String | c7c7120f2c07419\*\*ebdba0318c8 | 事件的唯一Id。 |
| openConfModel | Object | 会议id |  |
| payload | Object |  | 转写结果内容。 |
| header | Object |  | 转写结果头。 |
| timestamp | Long | 1733716797727 | 时间戳。 |
| bizType | String | minutes : 闪记 cloud\_record : 云录制 | 转写事件对应业务类型。 |
| recordId | String | 1232141245 | 转写事件对应。业务id |

### **事件体示例**

```
{
```

SyncHTTP/RDS推送

为RDS推送方式时，数据插入表open\_sync\_biz\_data\_medium中。

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| corp\_id | String | ding9f50b15bxxxx16741 | 企业corp\_id。 |
| biz\_id | String | 1663\*\*35567 | biz\_id无业务意义，幂等。 |
| biz\_type | Integer | 411 | 事件bizType。 |
| biz\_data | Object |  | 事件bizData介绍。 |

### **biz\_data数据示例(biz\_type=411)**

```
{
  "corp_id": "ding9f50b15bxxxx16741",
  "biz_id": "1663**35567",
  "biz_type": 411,
  "biz_data": {
    "recordId": "1232141245",
    "eventId": "c7c7120f2c07419**ebdba0318c8",
    "openConfModel": {
      "conferenceId": "67566af32fe07a026db9a940",
      "scheduleConferenceId": "5c7c9bb1-b256-4dc5-xxxx-xxxxxxxxxxxx"
    },
    "bizType": "minutes : 闪记  cloud_record : 云录制",
    "syncAction": "meeting_asr_result_event",
    "payload": {
      "result": "可以听到",
      "speakerUnionId": "lmvUrEjpboFrSMtgsiS9V3AiEiE",
      "words": [
        {
          "startTime": 32710,
          "text": "可",
          "endTime": 32770
```