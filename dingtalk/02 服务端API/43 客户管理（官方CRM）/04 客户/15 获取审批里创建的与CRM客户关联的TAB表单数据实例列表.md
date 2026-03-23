---
title: "获取审批里创建的与CRM客户关联的TAB表单数据实例列表新版SDK"
source: "https://open.dingtalk.com/document/development/api-getrelatedviewtabdata"
category: "服务端API / 客户管理（官方CRM） / 客户"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-getrelatedviewtabdata_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-getrelatedviewtabdata_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-09调用本接口，获取OA审批里创建的与CRM客户关联的tab表单的实例数据，包括实例的标题、实例创建时间、实例摘要信息。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 获取CRM自定义对象数据的接口访问权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=crm_1.0%23GetRelatedViewTabData) |
| 第三方企业应用 | 支持 | 获取CRM自定义对象数据的接口访问权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=crm_1.0%23GetRelatedViewTabData) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/crm/formRelatedTabs/datas/query HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "viewUserId" : "String",
  "nextToken" : Long,
  "formCode" : "String",
  "maxResults" : Integer,
  "relatedField" : "String",
  "relatedInstId" : "String"
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
| viewUserId | String | 否 | 企业下的用户 userid。 |
| nextToken | Long | 否 | 分页参数，下一条数据的位置。 |
| formCode | String | 否 | 表单代码，通过[获取审批中创建与CRM客户关联的TAB表单元数据](/document/development/api-getrelatedviewtabmeta)返回参数`formCode`获取。 |
| maxResults | Integer | 否 | 每页最大的个数 |
| relatedField | String | 否 | 关联字段，通过[获取审批中创建与CRM客户关联的TAB表单元数据](/document/development/api-getrelatedviewtabmeta)返回参数`relateComponentId`获取。 |
| relatedInstId | String | 否 | 相关实例代码。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| result | Object | 请求某个tab数据的响应。 |
| page | Object | 该tab页的具体数据。 |
| hasMore | Boolean | 是否还有更多数据。 |
| nextToken | Long | 下一条tab实例数据的位置。 |
| totalCount | Long | 实例总数。 |
| list | Array | 本次返回的tab实例数据列表。 |
| abstractMessage | String | 该条实例数据的摘要信息。 |
| createTime | Long | 创建时间戳（毫秒）。 |
| title | String | 该条实例数据的标题。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/crm/formRelatedTabs/datas/query HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:6765b981bd6c381ba3374a0bef0ba76d
Content-Type:application/json

{
  "viewUserId" : "manager6034",
  "nextToken" : 0,
  "formCode" : "PROC-62829702-A377-42A9-9CB3-E1C691A0CEDB",
  "maxResults" : 10,
  "relatedField" : "OpenDataField_OV2K4SOW2ZGG",
  "relatedInstId" : "u_dxcugzT0aPQvcK2PIkzQ00841721291058"
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
  "result" : {
    "page" : {
      "hasMore" : false,
      "nextToken" : 10,
      "totalCount" : 5,
      "list" : [ {
        "abstractMessage" : "西游四人组:孙悟空",
        "createTime" : 1726678923000,
        "title" : "王凯提交的楚衣的流程表单2"
      } ]
    }
  }
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | request.isNull | request请求参数为空 | request请求参数为空 |
| 401 | sys.error | 系统错误 | 系统错误 |
| 402 | params.isNull | corpId或者viewUserId为空 | corpId或者viewUserId为空 |
| 403 | crm.not.created | crm应用未安装 | crm应用未安装 |
| 405 | params.invalid | 无效的分页请求参数nextToken和maxResults | 无效的分页请求参数nextToken和maxResults |