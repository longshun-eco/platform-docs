---
title: "获取Agoal指定目标规则下的周期列表新版SDK"
source: "https://open.dingtalk.com/document/development/api-agoalobjectiveruleperiodlist"
category: "服务端API / Agoal"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-agoalobjectiveruleperiodlist_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-agoalobjectiveruleperiodlist_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-06调用本接口获取指定目标规则下的周期列表，返回信息包括周期的id、名称、起止时间和类型，数组列表形式返回，按照开始时间排序，越往前（接近现在时间）的排在前面，同样开始时间的周期再按照周期的间隔时间排序，间隔时间短的在前（季度3个月，排在半年6个月前）。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | Agoal周期读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=agoal_1.0%23AgoalObjectiveRulePeriodList) |
| 第三方企业应用 | 支持 | Agoal周期读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=agoal_1.0%23AgoalObjectiveRulePeriodList) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
GET /v1.0/agoal/objectiveRules/periodLists?objectiveRuleId=String HTTP/1.1
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
| objectiveRuleId | String | 是 | 目标规则id。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| requestId | String | 请求ID。 |
| success | Boolean | 请求是否成功。 |
| content | Array | 返回结果，周期列表。 |
| OpenObjectiveRulePeriodDTO | OpenObjectiveRulePeriodDTO | 周期对象。 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/agoal/objectiveRules/periodLists?objectiveRuleId=6444f5e9a4261c6e699dxxxx HTTP/1.1
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
  "requestId" : "7478B23C-80E8-1AD6-BE8C-09D480E0xxxx",
  "success" : true,
  "content" : [ {
    "periodId" : "6444f5e9a4261c6e699dxxxx",
    "name" : "2024年度",
    "startDate" : 1711900800000,
    "endDate" : 1743436799000,
    "periodType" : "season"
  } ]
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 500 | error.systemError | 系统异常 | 系统异常 |
| 500 | error.noPermission | 无权限 | 无权限 |