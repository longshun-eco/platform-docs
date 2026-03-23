---
title: "CRM客户动态"
source: "https://open.dingtalk.com/document/development/crm-customer-dynamics"
category: "事件订阅 / 客户管理"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-crm-customer-dynamics_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-crm-customer-dynamics_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-28

## 事件信息

|  |  |
| --- | --- |
| 名称 | 值 |
| 中文名称 | CRM客户动态 |
| 英文名称 | crm\_customer\_track |

## 功能描述

CRM客户动态相关信息发生变更时，钉钉通过事件订阅的方式将CRM客户动态相关变更内容推送给开发者。CRM客户动态事件数据推送说明。

## 支持应用类型

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | Stream模式推送 | HTTP推送 | SyncHTTP/RDS推送 |
| 第三方企业应用 | 支持 | 不支持 | 支持 |

## 事件体描述

Stream模式推送

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| eventUnifiedAppId | String | bbb381b6-f01xxxxx58daac | 统一应用身份Id。 |
| eventCorpId | String | ding9f50b15bxxxx16741 | 事件所属的corpId。 |
| eventType | String | crm\_customer\_track | 事件类型。 |
| eventId | String | c7c7120f2c07419\*\*ebdba0318c8 | 事件的唯一Id。 |
| eventBornTime | Long | 1683533823336 | 事件生成时间。 |
| data | Object |  | 事件体data。 |

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
| biz\_type | Integer | 133 | 事件bizType。 |
| biz\_data | Object |  | 事件bizData介绍。 |

### **biz\_data数据示例(biz\_type=133)**

```json
{
  "corp_id": "ding9f50b15bxxxx16741",
  "biz_id": "1663**35567",
  "biz_type": 133,
  "biz_data": {
    "eventId": "c7c7120f2c07419**ebdba0318c8",
    "syncAction": "crm_customer_track",
    "tracks": [
      {
        "creator": "manager1234",
        "corpId": "ding9axxx",
        "customerId": "84c75568-xxx-xxx",
        "subType": 0,
        "type": 107,
        "gmtCreate": 1630474492814
      }
    ]
  }
}
```