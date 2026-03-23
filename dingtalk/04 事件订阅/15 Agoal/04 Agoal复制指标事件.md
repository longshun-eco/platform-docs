---
title: "Agoal复制指标事件"
source: "https://open.dingtalk.com/document/development/events-agoal-indicator-copy"
category: "事件订阅 / Agoal"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-events-agoal-indicator-copy_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-events-agoal-indicator-copy_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-06

## 事件信息

| 名称 | 值 |
| --- | --- |
| 中文名称 | Agoal复制指标事件 |
| 英文名称 | agoal\_indicator\_copy |

## 功能描述

Agoal复制指标事件：当Agoal管理员在Agoal中复制指标时，会发送事件通知订阅方被复制指标及复制生成的指标信息，主要是用来给三方合作伙伴使用，合作伙伴接收事件以同步被被复制指标及复制生成的指标相关信息。

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
| eventType | String | agoal\_indicator\_copy | 事件类型。 |
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
| EventType | String | agoal\_indicator\_copy | 事件英文名称。 |
| EventTime | Long | 1663143335567 | 事件发生的时间。 |
| CorpId | String | ding9f50b15bxxxx16741 | 企业corpId。 |
| BizId | String | 1663\*\*35567 | 无业务意义，幂等。 |
| eventId | String | c7c7120f2c07419\*\*ebdba0318c8 | 事件的唯一Id。 |
| corpid | String | ding23980uodfijladkfja | 钉钉组织ID |
| bizid | String | djk23894jfkleuid8djf | 业务执行trace id |
| event\_time | String | 23124234234234 | 事件发生时的时间戳 |
| body | Object |  |  |

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
| biz\_type | Integer | 453 | 事件bizType。 |
| biz\_data | Object |  | 事件bizData介绍。 |

### **biz\_data数据示例(biz\_type=453)**

```json
{
  "corp_id": "ding9f50b15bxxxx16741",
  "biz_id": "1663**35567",
  "biz_type": 453,
  "biz_data": {
    "eventId": "c7c7120f2c07419**ebdba0318c8",
    "corpid": "ding23980uodfijladkfja",
    "syncAction": "agoal_indicator_copy",
    "bizid": "djk23894jfkleuid8djf",
    "body": {
      "code": "code_k8j7h9j6h8kk987",
      "origin_code": "code_k8j7h9j6h8kk987"
    },
    "event_time": "23124234234234"
  }
}
```