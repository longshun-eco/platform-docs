---
title: "批量获取表单模板schema（包含表单和流程配置信息）新版SDK"
source: "https://open.dingtalk.com/document/development/api-premiumqueryschemaandprocessbycodelist"
category: "服务端API / OA审批 / 高级版专享接口 / 官方 OA 审批 / 审批表单"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-premiumqueryschemaandprocessbycodelist_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-premiumqueryschemaandprocessbycodelist_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-11调用本接口，根据processCode列表批量获取表单模板schema相关信息（包含表单和流程配置信息）。

### 特别提醒

**说明**

当前接口为OA高级版专享接口，升级OA高级版可用，可满足更高级的开发需求，响应个性化的业务场景查看全部[专享OpenAPI](/document/development/description-of-new-oa-approval-premium-exclusive-openapi-and-solutions)。

### 接口功能介绍

例如，根据processCode列表批量获取表单模板schema相关信息（包含表单和流程配置信息），接口调用效果如下图所示。

![[development-api-premiumqueryschemaandprocessbycodelist_O1CN01FCBFTJ25wjHBznqCI_!!6000000007591-0-tps-1235-967.jpg]]

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | OA审批工作流读写权限（OA高级版专享） | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=workflow_1.0%23PremiumQuerySchemaAndProcessByCodeList) |
| 第三方企业应用 | 暂不支持 | 暂不支持 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/workflow/premium/processes/schemas/batchQuery HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "processCodes" : [ "String" ]
}
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 |

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| processCodes | Array of String | 是 | 模板code。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| result | Array | 返回结果。 |
| processCode | String | 模板code。 |
| formUuid | String | 表单formUuid。 |
| bizCategoryId | String | 模板业务类型标识。 |
| processId | Long | 流程processId。 |
| appUuid | String | 表单应用 uuid 或者 企业corpId。 |
| name | String | 模板名称。 |
| memo | String | 模板描述。 |
| icon | String | 图标icon地址。 |
| status | String | 模板状态：   * PUBLISHED：启用 * INVALID：停用 * SAVED：草稿 |
| creatorUserId | String | 模板创建人的userId。 |
| modifierUserId | String | 模板修改人的userId。 |
| createTime | Long | 模板创建时间。 |
| modifyTime | Long | 模板创建时间。 |
| schemaContent | String | 表单schema内容，json字符串。 |
| processConfig | String | 流程配置schema内容，json字符串。 |
| success | Boolean | 接口请求是否成功。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/workflow/premium/processes/schemas/batchQuery HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:f31f78b59d9438b9859e40xxxx9882f0
Content-Type:application/json

{
  "processCodes" : [ "Proc-123" ]
}
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
  "result" : [ {
    "processCode" : "PROC-17428B8C-6C60-470E-xxxx-64F1037AE067",
    "formUuid" : "FORM-28215C3E-00E3-4118-xxxx-4091F828AF2F",
    "bizCategoryId" : "hrm.xxx",
    "processId" : 123,
    "appUuid" : "ding123",
    "name" : "示例模板",
    "memo" : "模板描述1",
    "icon" : "https//:xxx",
    "status" : "PUBLISHED",
    "creatorUserId" : "userId123",
    "modifierUserId" : "userId123",
    "createTime" : 1638326995000,
    "modifyTime" : 1638326995000,
    "schemaContent" : "{\\\"commentHiddenForProposer\\\":\\\"\\\",\\\"commentRequired\\\":\\\"\\\",\\\"icon\\\":\\\"timefades#red\\\",\\\"commentDescription\\\":\\\"\\\",\\\"description\\\":\\\"支持地址控件\\\",\\\"title\\\":\\\"官方OA审批-POP-2025-0109\\\",\\\"items\\\":[{\\\"componentName\\\":\\\"TimeAndLocationField\\\",\\\"props\\\":{\\\"label\\\":[\\\"当前时间\\\",\\\"当前地点\\\"],\\\"id\\\":\\\"TimeAndLocationField_1CVHM5TIIWR9C\\\",\\\"required\\\":false}},{\\\"componentName\\\":\\\"TextField\\\",\\\"props\\\":{\\\"placeholder\\\":\\\"请输入\\\",\\\"label\\\":\\\"单行输入框\\\",\\\"id\\\":\\\"TextField_17EZKEGSOCTC0\\\",\\\"required\\\":false}}]}",
    "processConfig" : "{\\\"name\\\":\\\"发起人\\\",\\\"type\\\":\\\"start\\\",\\\"nodeId\\\":\\\"sid-startevent\\\",\\\"childNode\\\":{\\\"name\\\":\\\"审批人\\\",\\\"prevId\\\":\\\"sid-startevent\\\",\\\"type\\\":\\\"approver\\\",\\\"nodeId\\\":\\\"sid-1234_5678\\\",\\\"properties\\\":{\\\"activateType\\\":\\\"ONE_BY_ONE\\\",\\\"approvalType\\\":\\\"MANUAL\\\"}}}"
  } ],
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalidProcessCode | 审批模板processCode不能为空或超过最大数量限制 | 请检查processCode参数传值是否正确 |
| 400 | internalError | %s | 系统内部异常 |
| 400 | oaplus.query.limit | 请求过于频繁，稍后重试 | 企业访问并发超过限制 |
| 400 | benefit.status.invalid | 权益校验失败，未开通或过期 | 权益校验 |
| 400 | benefit.query.error | 权益查询失败 | 权益系统查询失败 |
| 400 | userNotExist | 用户不存在 | 请检查当前用户是否归属于当前组织 |
| 400 | processNotExist | 审批模板不存在 | 请检查processCode参数传值是否正确 |
| 500 | systemError | 系统异常 | 系统异常 |