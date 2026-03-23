---
title: "Teambiton工时变更事件"
source: "https://open.dingtalk.com/document/development/event-project-worktime-updated"
category: "事件订阅 / 协同 / 项目管理"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-event-project-worktime-updated_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-event-project-worktime-updated_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

## 事件信息

|  |  |
| --- | --- |
| 名称 | 值 |
| 中文名称 | Teambiton工时变更事件 |
| 英文名称 | project\_worktime\_updated |

## 功能描述

当Teambiton项目中工时属性内容发生更新时，钉钉通过事件订阅的方式将对应的项目中工时属性内容的变更推送给开发者，用于监听项目中工时属性更新的信息。

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
| eventType | String | project\_worktime\_updated | 事件类型。 |
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
| EventType | String | project\_worktime\_updated | 事件英文名称。 |
| EventTime | Long | 1663143335567 | 事件发生的时间。 |
| CorpId | String | ding9f50b15bxxxx16741 | 企业corpId。 |
| BizId | String | 1663\*\*35567 | 无业务意义，幂等。 |
| eventId | String | c7c7120f2c07419\*\*ebdba0318c8 | 事件的唯一Id。 |
| eventSubType | String | worktime.create | 事件子类型：   * **worktime.create**：工时创建。 * **worktime.approve**：工时审批。 |
| executorId | String | 0715153011125xxxx | 工时执行人。 |
| userId | String | 0715153011125xxxx | 操作人。 |
| taskId | String | 63c7f91f6ff268bcab40xxxx | tb任务id。 |
| workTimeIds | Array<String> |  | 工时id集合。 |
| workTime | Integer | 100000 | 实际工时数，单位：ms。 |
| dates | String | 2023-04-13T00:00:00Z | 填报日期。 |
| approveOpenId | String | 63c7f91f6ff268bcab40xxxx | tb侧关联ID，回写状态时入参。 |
| action | String | re-submit | 触发动作：   * **create**：创建时触发。 * **re-submit**：再次提交。 |
| created | String | 2023-04-13T00:00:00Z | 创建时间。 |
| updated | String | 2023-04-13T00:00:00Z | 更新时间。 |

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
| biz\_type | Integer | 297 | 事件bizType。 |
| biz\_data | Object |  | 事件bizData介绍。 |

### **biz\_data数据示例(biz\_type=297)**

```json
{
  "corp_id": "ding9f50b15bxxxx16741",
  "biz_id": "1663**35567",
  "biz_type": 297,
  "biz_data": {
    "eventId": "c7c7120f2c07419**ebdba0318c8",
    "eventSubType": "worktime.create",
    "syncAction": "project_worktime_updated",
    "executorId": "0715153011125xxxx",
    "created": "2023-04-13T00:00:00Z",
    "approveOpenId": "63c7f91f6ff268bcab40xxxx",
    "dates": "2023-04-13T00:00:00Z",
    "userId": "0715153011125xxxx",
    "workTime": 100000,
    "action": "re-submit",
    "updated": "2023-04-13T00:00:00Z",
    "taskId": "63c7f91f6ff268bcab40xxxx",
    "workTimeIds": [
      "63c7f91f6ff268bcab40xxxx"
    ]
  }
```