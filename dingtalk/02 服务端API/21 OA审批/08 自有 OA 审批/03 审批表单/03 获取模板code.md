---
title: "获取模板code新版SDK"
source: "https://open.dingtalk.com/document/development/obtain-the-template-code"
category: "服务端API / OA审批 / 自有 OA 审批 / 审批表单"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-the-template-code_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-the-template-code_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-24调用本接口，可实现根据审批模板名称获取对应的模板Processcode。

## 权限

要调用此API，需要以下权限之一。

| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| --- | --- | --- | --- |
| 企业内部应用 | 支持 | 工作流模板读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=workflow_1.0%23GetProcessCodeByName) |
| 第三方企业应用 | 支持 | 工作流模板读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=workflow_1.0%23GetProcessCodeByName) |
| 第三方个人应用 | 暂不支持 | 工作流模板读权限 | 暂不支持 |

## 请求方法

```
GET /v1.0/workflow/processCentres/schemaNames/processCodes?name=String HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Query参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| name | String | 是 | 模板名称，最大长度64字符，可通过[创建或更新审批模版](https://open.dingtalk.com/document/development/create-or-update-approval-templates-new)接口入参字段表单模板名称`name`字段获取。 |

## 返回参数

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| result | Object | 表单模板信息。 |
| processCode | String | 表单模板的code。 |
| gmtModified | String | 更新时间。 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/workflow/processCentres/schemaNames/processCodes?name=名称 HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:6d1bxxxx
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
    "processCode" : "PROC-abcdef-example",
    "gmtModified" : "2024-03-22T11:50Z"
  }
}
```

## 错误码

| HttpCode | 错误码 | 错误信息 | 说明 |
| --- | --- | --- | --- |
| 400 | permission.error | 没有访问权限 | 没有访问权限 |
| 400 | process.error | 模板不存在 | 模板不存在 |
| 400 | needAuth | 没有发起审批的权限 | 没有发起审批的权限 |
| 400 | invalidAgentId | 无效的微应用ID | 无效的微应用ID |
| 400 | invalidSuiteKey | 无效的suiteKey | 无效的suiteKey |
| 400 | internalError | %s | 系统内部异常 |
| 500 | system.error | 系统错误 | 系统错误 |