---
title: "获取Agoal指定部门下的计分卡维度和指标id新版SDK"
source: "https://open.dingtalk.com/document/development/api-getdeptscorecardindicator"
category: "服务端API / Agoal"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-getdeptscorecardindicator_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-getdeptscorecardindicator_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-06调用本接口获取指定部门下计分卡的维度和指标，返回对象包括维度id、指标id，以数组列表形式返回。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | Agoal计分卡读取权限。 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=agoal_1.0%23GetDeptScoreCardIndicator) |
| 第三方企业应用 | 支持 | Agoal计分卡读取权限。 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=agoal_1.0%23GetDeptScoreCardIndicator) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
GET /v1.0/agoal/scorecards/departments/indicators?dingTeamId=String HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Query参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| dingTeamId | String | 否 | 部门openId。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| requestId | String | 请求ID。 |
| success | Boolean | 是否成功。 |
| content | OpenScoreCardDimensionDTO | 包含维度和指标id。 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/agoal/scorecards/departments/indicators?dingTeamId=853434729 HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:9801a354e3d03539baa83e5f275axxxx
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
  "requestId" : "ACA7BAAA-BA6F-76F3-8A1B-EF4A37E589E9",
  "success" : true,
  "content" : {
    "dimensionList" : [ {
      "indicatorIdList" : [ ]
    } ]
  }
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 500 | error.systemError | 系统异常 | 系统异常 |
| 500 | error.emptyScoreCard | 部门下没有计分卡 | 部门下没有计分卡 |