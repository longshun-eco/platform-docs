---
title: "根据userId查询人员的标签信息新版SDK"
source: "https://open.dingtalk.com/document/development/you-can-call-this-operation-to-retrieve-the-user-tag"
category: "服务端API / 专属钉钉 / 产业互联"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-you-can-call-this-operation-to-retrieve-the-user-tag_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-you-can-call-this-operation-to-retrieve-the-user-tag_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23调用本接口查询上下游组织内人员的标签信息。

**说明**

本接口目前仅支持专属钉钉企业调用，如何申请开通专属钉钉，请参考[专属钉钉开通流程](https://alidocs.dingtalk.com/i/p/Y7kmbokZp3pgGLq2/docs/KOEmgBoGwD78vZrbzdR68ndLerP9b30a?spm=ding_open_doc.document.0.0.7f40722fMQjJ5n)。

例如，上下游测试组织内有个合作伙伴为**关联组织**。调用本接口，可获取关联组织根部门下的某员工信息。如下图所示，该员工所在的部门名称为**关联组织**，伙伴编码为**partner1**，一级伙伴类型为**供应商**。

![[development-you-can-call-this-operation-to-retrieve-the-user-tag_O1CN01czctRG24J3N7oj3uL_!!6000000007369-2-tps-2704-1158.png]]

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 伙伴钉部门信息读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=exclusive_1.0%23QueryPartnerInfo) |
| 第三方企业应用 | 支持 | 伙伴钉部门信息读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=exclusive_1.0%23QueryPartnerInfo) |
| 第三方个人应用 | 暂不支持 | 伙伴钉部门信息读权限 | 暂不支持 |

## 请求方法

```
GET /v1.0/exclusive/partners/users/{userId} HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Path参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| userId | String | 是 | 用户userId，可调用[查询用户详情](/document/development/query-user-details)接口获取。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| partnerDeptList | Array | 员工所在的部门列表。 |
| title | String | 部门名称。 |
| value | String | 部门ID。 |
| memberCount | Long | 成员数。 |
| partnerNum | String | 伙伴编码。 |
| partnerLabelModelLevel1 | Object | 一级伙伴信息。 |
| labelId | Long | 一级伙伴标签ID。 |
| labelname | String | 一级伙伴类型。 |
| partnerLabelList | Array | 伙伴类型下的角色列表。 |
| id | Long | 伙伴标签下的角色ID。 |
| name | String | 伙伴标签下的角色名称。 |
| userId | String | 员工userId。  **说明**  如果partnerLabelList为空，该字段返回为空。 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/exclusive/partners/users/001 HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:xxxxx
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
// This file is auto-generated, don't edit it
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
  "partnerDeptList" : [ {
    "title" : "测试组织1",
    "value" : "123",
    "memberCount" : 111,
    "partnerNum" : "1",
    "partnerLabelModelLevel1" : {
      "labelId" : 111,
      "labelname" : "测试"
    }
  } ],
  "partnerLabelList" : [ {
    "id" : 111,
    "name" : "测试"
  } ],
  "userId" : "111111"
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | param.not.found | 参数不能为空 | 参数不能为空 |
| 500 | user.not.found | 该员工不在企业中 | 该员工不在企业中 |
| 500 | hava.no.auth | 该员工无企业权限 | 该员工无企业权限 |