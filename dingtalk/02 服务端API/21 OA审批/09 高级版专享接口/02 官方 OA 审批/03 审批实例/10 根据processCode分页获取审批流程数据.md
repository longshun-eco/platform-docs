---
title: "根据processCode分页获取审批流程数据新版SDK"
source: "https://open.dingtalk.com/document/development/api-premiumgetprocessinstances"
category: "服务端API / OA审批 / 高级版专享接口 / 官方 OA 审批 / 审批实例"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-premiumgetprocessinstances_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-premiumgetprocessinstances_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-10调用本接口根据processCode分页获取审批流程数据。

### 特别提醒

**说明**

当前接口为OA高级版专享接口，升级OA高级版可用，可满足更高级的开发需求，响应个性化的业务场景。[查看全部专享OpenAPI](https://open.dingtalk.com/document/development/description-of-new-oa-approval-premium-exclusive-openapi-and-solutions)

### 接口调用说明

* 当前接口针对OA高级版客户可支持查询最多5年内的实例数据（即startTime时间距当前时间不能超过5年）。
* 如果只传入**startTime**参数，要求时间距离当前时间不能超过120天（即一次查询最多只能查询120天的数据），**endTime**不传则默认取当前时间。
* 如果传入**startTime**参数和**endTime**参数，要求时间范围不能超过120天，同时**startTime**时间距当前时间不能超过5年（即最多可支持查询5年内的实例数据）。
* 批量获取的实例ID个数（循环获取），最多不能超过10000个，建议分多次获取。

### 接口功能介绍

调用本接口根据表单的processCode，分页获取表单审批流程数据。

例如，依次单击**工作台** > **OA审批** > **首页** > **点击进入表单模板** > **查看数据**，查看对应模板数据，如下图所示。

调用本接口，可获取指定表单模板下的详情信息，包括表单提交时间、表单实例ID、提交人姓名、表单实例详情数据等信息。

![[development-api-premiumgetprocessinstances_批量查询模板数据.png]]

## 权限

要调用此API，需要以下权限之一。

| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| --- | --- | --- | --- |
| 企业内部应用 | 支持 | OA审批工作流读写权限（OA高级版专享） | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=workflow_1.0%23PremiumGetProcessInstances) |
| 第三方企业应用 | 暂不支持 | 暂不支持 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
GET /v1.0/workflow/premium/processes/pages/instances?nextToken=String&maxResults=Long&startTimeInMills=Long&endTimeInMills=Long&processCode=String&appUuid=String HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，企业内部应用可调用[获取企业内部应用的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 |

## Query参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| nextToken | String | 否 | 分页游标。   * 如果是首次调用，该参数传1。 * 如果是非首次调用，该参数传上次调用时返回的nextToken。 |
| maxResults | Long | 是 | 分页参数，每页大小，最多传20。 |
| startTimeInMills | Long | 是 | 审批实例开始时间，Unix时间戳，单位毫秒。  **说明**   * 例如，获取审批单发起时间在2020.4.10-2020.4.14之间，该值传2020.4.10 00:00:00对应的时间戳1586448000000。 * 针对OA高级版用户，**startTime**时间距当前时间不能超过5年，即最多可支持查询5年内的实例数据。 * 如果只传入**startTime**参数，要求时间距离当前时间不能超过120天，即一次查询最多只能查询120天的数据。 |
| endTimeInMills | Long | 否 | 审批实例结束时间，Unix时间戳，单位毫秒。  **说明**   * 例如，获取审批单发起时间在2020.4.10-2020.4.14之间，该值传2020.4.14 23:59:59对应的时间戳1586879999000。 * **endTime**不传则默认取当前时间。 |
| processCode | String | 是 | 模板ID。   * 通过调用[创建或更新审批表单模板](https://open.dingtalk.com/document/development/create-an-approval-form-template)接口获取。 * 通过[OA审批概述-名词解释](https://open.dingtalk.com/document/development/workflow-overview)获取。 |
| appUuid | String | 否 | 应用搭建ID，默认可传企业corpId值。 |

## 返回参数

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| result | Object | 返回结果。 |
| nextToken | String | 下一次请求的分页游标。 |
| hasMore | Boolean | 是否有更多数据。 |
| maxResults | Long | 分页大小。 |
| list | Array | 审批流程数据列表。 |
| processInstanceId | String | 流程实例ID。 |
| mainProcessInstanceId | String | 主单实例ID。 |
| finishTime | Long | 审批结束时间。 |
| finishTimeInMills | Long | 审批结束时间，Unix时间戳，单位毫秒。 |
| attachedProcessInstanceIds | String | 附属单信息。 |
| businessId | String | 审批单编号。 |
| title | String | 审批单标题。 |
| originatorDeptId | String | 发起人部门ID。  **说明**  默认值-1：表示企业根部门。 |
| result | String | 审批结果，取值：   * \*\* agree\*\*：同意 * \*\* refuse\*\*：拒绝 |
| createTime | Long | 审批单创建时间。 |
| createTimeInMills | Long | 审批单创建时间，Unix时间戳，单位毫秒。 |
| originatorUserid | String | 发起者userId。 |
| status | String | 审批单状态，取值：   * **RUNNING**：审批中 * **TERMINATED**：撤销 * **COMPLETED**：审批完成 |
| formComponentValues | Array | 表单实例数据列表。 |
| name | String | 控件名称。 |
| id | String | 控件ID。 |
| value | String | 控件数据。 |
| extValue | String | 控件扩展数据。 |
| operationRecords | Array | 审批单操作记录列表。 |
| timestamp | Long | 操作时间戳。 |
| result | String | 操作结果，取值：   * **AGREE**：同意 * **REFUSE**：拒绝 * **NONE**：未知 |
| operationType | String | 操作类型，取值：   * **EXECUTE\_TASK\_NORMAL**：正常执行任务 * **EXECUTE\_TASK\_AGENT**：代理人执行任务 * **APPEND\_TASK\_BEFORE**：前加签任务 * **APPEND\_TASK\_AFTER**：后加签任务 * **REDIRECT\_TASK**：转交任务 * **START\_PROCESS\_INSTANCE**：发起流程实例 * **TERMINATE\_PROCESS\_INSTANCE**：终止(撤销)流程实例 * **FINISH\_PROCESS\_INSTANCE**：结束流程实例 * **ADD\_REMARK**：添加评论 |
| userId | String | 操作人userId。 |
| remark | String | 评论。 |
| attachments | Array | 评论附件列表。 |
| fileName | String | 附件名称。 |
| fileSize | String | 文件大小。 |
| fileId | String | 附件钉盘ID。 |
| fileType | String | 文件类型。 |
| tasks | Array | 任务列表。 |
| userId | String | 任务处理人。 |
| status | String | 任务状态，取值：   * **RUNNING**：处理中 * **TERMINATED**：撤销 * **COMPLETED**：完成 * **CANCELED**：取消 |
| result | String | 任务结果，取值：   * **AGREE**：同意 * **REFUSE**：拒绝 * **REDIRECTED**：转交 * **NONE**：未知 |
| createTimestamp | Long | 任务创建时间戳 |
| finishTimestamp | Long | 任务结束时间戳 |
| taskId | Long | 任务Id |
| activityId | String | 节点id |

## 示例

**请求示例**

HTTP

```
GET /v1.0/workflow/premium/processes/pages/instances?nextToken=1&maxResults=10&startTimeInMills=1631289600000&endTimeInMills=1633795200000&processCode=PROC-C53-example&appUuid=SWAPP-4C2F4B-example HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:BWExxx
Content-Type:application/json
```

Java

```
// This file is auto-generated, don't edit it. Thanks.
```

Python

```
# -*- coding: utf-8 -*-
```

PHP

```
php</code
```

Go

```
// This file is auto-generated, don't edit it. Thanks.
```

Node.js

```
'use strict';
```

C#

```
// This file is auto-generated, don't edit it. Thanks.
```

**返回示例**

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "result" : {
    "nextToken" : "10",
    "hasMore" : true,
    "maxResults" : 20,
    "list" : [ {
      "processInstanceId" : "abcdse-dse-example",
      "mainProcessInstanceId" : "dcdse-dae2fd2-example",
      "finishTime" : 1633795200000,
      "finishTimeInMills" : 1633795200000,
      "attachedProcessInstanceIds" : "cdef-dae2fd2-example",
      "businessId" : "202110111558000355024",
      "title" : "员工A提交的小肖审批单",
      "originatorDeptId" : "默认-1，企业根部门",
      "result" : "agree同意，refuse拒绝",
      "createTime" : 1635165470201,
      "createTimeInMills" : 1635165470201,
      "originatorUserid" : "staff1234",
```

## 错误码

| HttpCode | 错误码 | 错误信息 | 说明 |
| --- | --- | --- | --- |
| 400 | userIdList.error | illegal userIdList | 查询userId列表错误 |
| 400 | timeStamp.invalid | illegal timestamp | 查询时间错误 |
| 400 | pageSize.invalid | illegal pageSize | 分页大小错误 |
| 400 | pageIndex.invalid | illegal pageIndex | 游标错误 |
| 400 | permission.error | no permission | 没有权限 |
| 400 | processCode.error | processCode query error | 模板编码查询错误 |
| 400 | internalError | %s | 系统内部异常 |
| 400 | oaplus.query.limit | 请求过于频繁，稍后重试 | 企业访问并发超过限制 |
| 400 | benefit.status.invalid | 权益校验失败，未开通或过期 | 权益校验 |
| 400 | benefit.query.error | 权益查询失败 | 权益系统查询失败 |
| 500 | system.error | system error | 系统错误 |