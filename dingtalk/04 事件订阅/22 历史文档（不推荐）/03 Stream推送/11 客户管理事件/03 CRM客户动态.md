---
title: "CRM客户动态"
source: "https://open.dingtalk.com/document/development/crm-customer-dynamic-event-stream"
category: "事件订阅 / 历史文档（不推荐） / Stream推送 / 客户管理事件"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-crm-customer-dynamic-event-stream_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-crm-customer-dynamic-event-stream_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-16

## 事件信息

| 名称 | 值 |
| --- | --- |
| 中文名称 | CRM客户动态 |
| 英文名称 | crm\_customer\_track |

## 功能描述

CRM客户动态相关信息发生变更时，钉钉通过事件订阅的方式将CRM客户动态相关变更内容推送给开发者。eventType为crm\_customer\_track，表示CRM客户动态事件数据。

## 支持应用类型

| 应用类型 | 是否支持 |
| --- | --- |
| 企业内部应用 | 不支持 |
| 第三方企业应用 | 支持 |

## **事件体描述**

### header部分

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| eventUnifiedAppId | String | bbb381b6-f01xxxxx58daac | 统一应用身份Id。 |
| eventCorpId | String | ding9f50b15bxxxx16741 | 事件所属的corpId。 |
| eventType | String | crm\_customer\_track | 事件类型。 |
| eventId | String | c7c7120f2c07419\*\*ebdba0318c8 | 事件的唯一Id。 |
| eventBornTime | Long | 1683533823336 | 事件生成时间。 |

### data部分(事件业务信息)

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| tracks | Array<Object> |  | 客户动态相关的数据变更列表。 |

### **事件体数据示例如下:**

```json
{
  "eventUnifiedAppId": "bbb381b6-f01xxxxx58daac",
  "eventCorpId": "ding9f50b15bxxxx16741",
  "eventType": "crm_customer_track",
  "eventId": "c7c7120f2c07419**ebdba0318c8",
  "eventBornTime": 1683533823336,
  "data": {
    "tracks": [
      {
        "creator": "manager1234",
        "corpId": "ding9axxx",
        "customerId": "84c75568-xxx-xxx",
        "subType": 0,
        "gmtCreate": 1630474492814,
        "type": 107
      }
    ]
  }
}
```