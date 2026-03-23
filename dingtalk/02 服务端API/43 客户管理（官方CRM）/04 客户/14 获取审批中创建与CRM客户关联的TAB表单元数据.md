---
title: "获取审批中创建与CRM客户关联的TAB表单元数据新版SDK"
source: "https://open.dingtalk.com/document/development/api-getrelatedviewtabmeta"
category: "服务端API / 客户管理（官方CRM） / 客户"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-getrelatedviewtabmeta_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-getrelatedviewtabmeta_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-09调用本接口，获取OA审批里创建的与CRM客户关联的tab表单元数据，包括表单标题、关联的联系人控件id。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 获取CRM自定义对象数据的接口访问权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=crm_1.0%23GetRelatedViewTabMeta) |
| 第三方企业应用 | 支持 | 获取CRM自定义对象数据的接口访问权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=crm_1.0%23GetRelatedViewTabMeta) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/crm/formRelatedTabs/meta/query HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "formCode" : "String",
  "viewUserId" : "String"
}
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| formCode | String | 是 | 个人客户或者企业客户的表单代码 。 |
| viewUserId | String | 是 | 企业内的用户 userid。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| results | Array | 返回结果列表。 |
| formCode | String | 表单代码。 |
| relateComponentId | String | 相关联的组件id。 |
| tabTitle | String | tab的标题。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/crm/formRelatedTabs/meta/query HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:6765b981bd6c381ba3374a0bef0ba76d
Content-Type:application/json

{
  "formCode" : "PROC-CE6BDC9A-701A-4C41-B9CE-6D614DB80568",
  "viewUserId" : "manager6034"
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
  "results" : [ {
    "formCode" : "PROC-4EFE895D-A291-4A65-9FD6-99431604DF67",
    "relateComponentId" : "OpenDataField_K99RPMMRGJ40",
    "tabTitle" : "212"
  } ]
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | request.isNull | request请求参数为空 | request请求参数未传递空 |
| 401 | sys.error | 系统错误 | 系统错误 |
| 402 | params.isNull | corpId或者viewUserId为空 | corpId或者viewUserId为空 |
| 403 | crm.not.created | crm应用未安装 | crm应用未安装 |