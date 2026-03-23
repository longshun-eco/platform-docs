---
title: "CRM元数据"
source: "https://open.dingtalk.com/document/development/crm-metadata"
category: "事件订阅 / 历史文档（不推荐） / RDS推送/SyncHTTP推送 / 客户管理事件"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-crm-metadata_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-crm-metadata_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-16

## 事件信息

| 名称 | 值 |
| --- | --- |
| 中文名称 | CRM元数据 |
| 英文名称 | ding\_crm\_object\_meta |
| 事件BizType | 293 |

## 功能描述

客户管理元数据回调事件，当用户进入客户管理后台编辑并发布客户、联系人、跟进记录表单时会触发推送本事件。

![[development-crm-metadata_O1CN01GX0Gda1Ggf3dKNESN_!!6000000000652-2-tps-2268-1472.png]]

## 支持应用类型

| 应用类型 | 是否支持 |
| --- | --- |
| 企业内部应用 | 支持 |
| 第三方企业应用 | 支持 |

## **事件体描述**

### 企业内部应用

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| EventType | String | ding\_crm\_object\_meta | 事件英文名称 |
| EventTime | Long | 1663143335567 | 事件发生的时间 |
| CorpId | String | 1663\*\*351222567 | 企业corpId |
| BizId | String | 1663\*\*35567 | 无业务意义，幂等 |
| type | String | ding\_paas\_object\_update | 元数据事件类型：   * ding\_paas\_object\_create：创建元数据 * ding\_paas\_object\_update：更新元数据 * ding\_paas\_object\_delete：删除元数据 |
| objectName | String | crm\_customer | 元数据标识：   * crm\_customer：企业客户 * crm\_customer\_personal：个人客户 * crm\_contact：联系人 * crm\_follow\_record：跟进记录 |
| name | String | 企业客户 | 元数据名称。 |
| customized | Boolean | false | 是否自定义元数据：   * true：自定义 * false：标准 |
| status | String | PUBLISHED | 元数据状态：   * PUBLISHED：已发布 * INVALID：已停用 |
| fields | Array<Object> |  | 元数据字段列表。 |

### **事件体示例**

```
{
  "CorpId": "1663**351222567",
  "customized": false,
  "EventType": "ding_crm_object_meta",
  "EventTime": 1663143335567,
  "name": "企业客户",
  "objectName": "crm_customer",
  "type": "ding_paas_object_update",
  "fields": [
    {
      "customized": false,
      "quote": true,
      "referenceToCode": "PROC-2627EB94-8FD1-43D0-AC1D-214CBF2E6819",
      "relatedFormFields": [
        {
          "relatedFields": [
            {
              "customized": false,
              "name": "customer_name",
              "id": "TextField-K2U5DHAA",
              "label": "客户名称",
```

### 第三方企业应用(biz\_type=293)

数据为RDS和SyncHTTP推送的事件体，当为RDS推送方式时，数据插入表open\_sync\_biz\_data\_medium中。

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| corp\_id | String | 1663\*\*351222567 | 企业corp\_id |
| biz\_id | String | 1663\*\*35567 | biz\_id无业务意义，幂等 |
| biz\_type | Integer | 293 | 事件bizType |
| biz\_data | Object |  | 事件bizData介绍 |

### **biz\_data数据示例如下:**

```
{
  "customized": false,
  "syncAction": "ding_crm_object_meta",
  "name": "企业客户",
  "objectName": "crm_customer",
  "type": "ding_paas_object_update",
  "fields": [
    {
      "customized": false,
      "quote": true,
      "referenceToCode": "PROC-2627EB94-8FD1-43D0-AC1D-214CBF2E6819",
      "relatedFormFields": [
        {
          "relatedFields": [
            {
              "customized": false,
              "name": "customer_name",
              "id": "TextField-K2U5DHAA",
              "label": "客户名称",
              "type": "Text",
              "nillable": false
```