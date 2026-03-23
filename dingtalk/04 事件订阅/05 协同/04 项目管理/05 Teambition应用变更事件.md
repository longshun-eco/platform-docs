---
title: "Teambition应用变更事件"
source: "https://open.dingtalk.com/document/development/teamposition-application-change-event"
category: "事件订阅 / 协同 / 项目管理"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-teamposition-application-change-event_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-teamposition-application-change-event_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

**重要**

Teambition事件属于灰度阶段，如需使用请填写[宜搭申请单](https://kqu4sn.aliwork.com/o/teambition_event_apply)进行申请。

## **事件信息**

|  |  |
| --- | --- |
| **名称** | **值** |
| 中文名称 | Teambition应用变更事件 |
| 英文名称 | project\_project\_app\_changed |
| 事件BizType | 256 |

## 功能描述

当Teambiton项目应用发生变更时，钉钉通过事件订阅的方式将项目应用变更内容推送给开发者，用于监听Teambiton项目应用变更信息。

## **事件体描述**

### **企业内部应用**

#### 项目应用安装

|  |  |
| --- | --- |
| 参数 | 说明 |
| CorpId | 使用Teambition项目的企业corpId。 |
| EventType | 事件类型：   * **project\_project\_app\_changed**：Teambition应用变更事件 |
| EventTime | 事件发生的时间。 |
| BizId | Teambition项目的实例Id。 |
| eventSubType | 事件子类型：   * **tb.v3.project.application.create**：项目应用安装 |
| creatorId | 创建者userId。 |
| projectId | 项目Id。 |
| created | 创建时间。 |
| updated | 更新时间。 |
| applicationId | 应用id。 |

#### **事件体示例**

```json
{
  "CorpId": "dingc23b7b9682b4xxxx",
  "EventType": "project_project_app_changed",
  "EventTime": 1672046863855,
  "BizId": "tb_63a9690f89217deca9a3xxxx",
  "data": {
    "eventSubType": "tb.v3.project.application.create",
    "creatorId": "0715153011125xxxx",
    "projectId": "64ba333e4206372f3f5cxxxx",
    "created": "2022-12-26T09:27:43.733Z",
    "updated": "2022-12-26T09:27:43.733Z",
    "applicationId": "64ba333e4206372f3f5cxxxx"
  }
}
```

#### 项目应用卸载

|  |  |
| --- | --- |
| 参数 | 说明 |
| CorpId | 使用Teambition项目的企业corpId。 |
| EventType | 事件类型：   * **project\_project\_app\_changed**：Teambition应用变更事件 |
| EventTime | 事件发生的时间。 |
| BizId | Teambition项目的实例Id。 |
| eventSubType | 事件子类型：   * **tb.v3.project.application.delete**：项目应用卸载 |
| creatorId | 创建者userId。 |
| projectId | 项目Id。 |
| created | 创建时间。 |
| updated | 更新时间。 |
| applicationId | 应用id。 |

#### **事件体示例**

```json
{
  "CorpId": "dingc23b7b9682b4xxxx",
  "EventType": "project_project_app_changed",
  "EventTime": 1672046863855,
  "BizId": "tb_63a9690f89217deca9a3xxxx",
  "data": {
    "eventSubType": "tb.v3.project.application.delete",
    "creatorId": "0715153011125xxxx",
    "projectId": "64ba333e4206372f3f5cxxxx",
    "created": "2022-12-26T09:27:43.733Z",
    "updated": "2022-12-26T09:27:43.733Z",
    "applicationId": "64ba333e4206372f3f5cxxxx"
  }
}
```

### **第三方企业应用**

#### 项目应用安装

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| corp\_id | String | 企业corp\_id。 |
| biz\_id | String | biz\_id无业务意义，幂等。 |
| biz\_type | Integer | 事件bizType。 |
| biz\_data | Object | 事件bizData介绍。 |
| data | Object | 项目应用安装对象。 |
| syncAction | String | 事件英文名。 |
| eventSubType | String | 事件子类型：   * **tb.v3.project.application.create**：项目应用安装 |
| creatorId | String | 创建者userId。 |
| projectId | String | 项目Id。 |
| created | String | 创建时间。 |
| updated | String | 更新时间。 |
| applicationId | String | 应用id。 |

#### **biz\_data数据示例如下：**

```json
{
  "data": {
    "syncAction": "project_project_app_changed",
    "eventSubType": "tb.v3.project.application.create",
    "creatorId": "0715153011125xxxx",
    "projectId": "64ba333e4206372f3f5cxxxx",
    "created": "2022-12-26T09:27:43.733Z",
    "updated": "2022-12-26T09:27:43.733Z",
    "applicationId": "64ba333e4206372f3f5cxxxx"
  }
}
```

#### 项目应用卸载

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| corp\_id | String | 企业corp\_id。 |
| biz\_id | String | biz\_id无业务意义，幂等。 |
| biz\_type | Integer | 事件bizType。 |
| biz\_data | Object | 事件bizData介绍。 |
| data | Object | 项目应用安装对象。 |
| syncAction | String | 事件英文名。 |
| eventSubType | String | 事件子类型：   * **tb.v3.project.application.delete**：项目应用卸载 |
| creatorId | String | 创建者userId。 |
| projectId | String | 项目Id。 |
| created | String | 创建时间。 |
| updated | String | 更新时间。 |
| applicationId | String | 应用id。 |

#### **biz\_data数据示例如下：**

```json
{
  "data": {
    "syncAction": "project_project_member_changed",
    "eventSubType": "tb.v3.project.application.delete",
    "creatorId": "0715153011125xxxx",
    "projectId": "64ba333e4206372f3f5cxxxx",
    "created": "2022-12-26T09:27:43.733Z",
    "updated": "2022-12-26T09:27:43.733Z",
    "applicationId": "64ba333e4206372f3f5cxxxx"
  }
}
```