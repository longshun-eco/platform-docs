---
title: "Agoal个人目标新增事件"
source: "https://open.dingtalk.com/document/development/agoal-personal-goals-have-added-new-events"
category: "事件订阅 / Agoal"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-agoal-personal-goals-have-added-new-events_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-agoal-personal-goals-have-added-new-events_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-12-05

## 事件信息

| 名称 | 值 |
| --- | --- |
| 中文名称 | Agoal个人目标新增事件 |
| 英文名称 | agoal\_objective\_add |

## 功能描述

Agoal个人目标新增事件：当用户在Agoal的员工目标下录入目标时，会发送事件通知订阅方个人目标的信息，主要是用来给三方合作伙伴使用，合作伙伴接收事件以同步更新目标相关信息。

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
| eventType | String | agoal\_objective\_add | 事件类型。 |
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
| EventType | String | agoal\_objective\_add | 事件英文名称。 |
| EventTime | Long | 1663143335567 | 事件发生的时间。 |
| CorpId | String | ding9f50b15bxxxx16741 | 企业corpId。 |
| BizId | String | 1663\*\*35567 | 无业务意义，幂等。 |
| eventId | String | c7c7120f2c07419\*\*ebdba0318c8 | 事件的唯一Id。 |
| body | Object |  |  |
| corpid | String | ding9f50b15bxxxx16741 | 钉钉组织ID |
| bizid | String | dif3423847924dds | 业务执行trace id |
| eventTime | String | 1773423492 | 事件发生时的时间戳 |

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
| biz\_type | Integer | 422 | 事件bizType。 |
| biz\_data | Object |  | 事件bizData介绍。 |

### **biz\_data数据示例(biz\_type=422)**

```json
{
  "corp_id": "ding9f50b15bxxxx16741",
  "biz_id": "1663**35567",
  "biz_type": 422,
  "biz_data": {
    "eventId": "c7c7120f2c07419**ebdba0318c8",
    "corpid": "ding9f50b15bxxxx16741",
    "syncAction": "agoal_objective_add",
    "bizid": "dif3423847924dds",
    "eventTime": "1773423492",
    "body": {
      "dingUserId": "2639400000-1812711000",
      "periodId": "662e006fe4b0f579bbcccccc",
      "objectiveId": "662e006fe4b0f579bbcxxxxx",
      "objectiveRuleId": "662e006fe4b0f579bbcbbbbb"
    }
  }
}
```