---
title: "视频会议状态变更App定向推送"
source: "https://open.dingtalk.com/document/development/events-meeting-status-change-target-push"
category: "事件订阅 / 音视频 / 视频/音频会议"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-events-meeting-status-change-target-push_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-events-meeting-status-change-target-push_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

## 事件信息

| 名称 | 值 |
| --- | --- |
| 中文名称 | 视频会议状态变更App定向推送 |
| 英文名称 | meeting\_status\_change\_target\_push |

## 功能描述

视频会议状态变更定向推送，目前支持定向推送通过开放接口创建的会议事件，定向推送给调用方所属的应用。

## 支持应用类型

| 应用类型 | Stream模式推送 | HTTP推送 | SyncHTTP/RDS推送 |
| --- | --- | --- | --- |
| 企业内部应用 | 支持 | 支持 | 不支持 |
| 第三方企业应用 | 支持 | 不支持 | 支持 |

## 事件体描述

Stream模式推送

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| eventUnifiedAppId | String | bbb381b6-f01xxxxx58daac | 统一应用身份Id。 |
| eventCorpId | String | ding9f50b15bxxxx16741 | 事件所属的corpId。 |
| eventType | String | meeting\_status\_change\_target\_push | 事件类型。 |
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
| EventType | String | meeting\_status\_change\_target\_push | 事件英文名称。 |
| EventTime | Long | 1663143335567 | 事件发生的时间。 |
| CorpId | String | ding9f50b15bxxxx16741 | 企业corpId。 |
| BizId | String | 1663\*\*35567 | 无业务意义，幂等。 |
| eventId | String | c7c7120f2c07419\*\*ebdba0318c8 | 事件的唯一Id。 |
| statusSeqNum | Integer | 1 | 会议、成员信息总体序列号, 用于区分消息顺序 |
| changeScene | String | conference\_created | 会议状态变化细分类型：   * conference\_created : 会议创建事件。 * conference\_closed : 会议关闭事件。 |
| openConfModel | Object |  | 会议信息。 |

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
| biz\_type | Integer | 348 | 事件bizType。 |
| biz\_data | Object |  | 事件bizData介绍。 |

### **biz\_data数据示例(biz\_type=348)**

```
{
  "corp_id": "ding9f50b15bxxxx16741",
  "biz_id": "1663**35567",
  "biz_type": 348,
  "biz_data": {
    "eventId": "c7c7120f2c07419**ebdba0318c8",
    "openConfModel": {
      "bizType": 0,
      "creatorId": "2iPOLxxxxx",
      "roomCode": "4272xxxxx",
      "title": "开放会议",
      "activeNum": 10,
      "creatorNick": "小钉",
      "attendNum": 15,
      "confDuration": 1000000,
      "conferenceId": "6321*******9b6ed40",
      "startTime": 1663293270000,
      "endTime": 1663294270000,
      "invitedNum": 20,
      "externalLinkUrl": "https://meeting.dingtalk.com/app?roomCode\u003d42726xxx\u0026token\u003d1_7ac9xxx",
      "scheduleConferenceId": "5ba0a5ce-xxxx-4a4f-bc68-xxxx81980eea",
```