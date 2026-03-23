---
title: "获取Agoal目标或关键结果关联的关键行动新版SDK"
source: "https://open.dingtalk.com/document/development/api-agoalobjectivekeyactionlist"
category: "服务端API / Agoal"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-agoalobjectivekeyactionlist_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-agoalobjectivekeyactionlist_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-06调用本接口获取Agoal指定目标或者关键结果下关联的关键行动，返回对象包括关键行动的id、名称和关联的链接。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | Agoal目标读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=agoal_1.0%23AgoalObjectiveKeyActionList) |
| 第三方企业应用 | 支持 | Agoal目标读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=agoal_1.0%23AgoalObjectiveKeyActionList) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
GET /v1.0/agoal/objectives/keyActionLists?objectiveId=String&keyResultId=String&dingUserId=String HTTP/1.1
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
| objectiveId | String | 是 | 查询的目标id。 |
| keyResultId | String | 否 | 查询的关键结果id。 |
| dingUserId | String | 是 | 查询的指定用户钉钉userId。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| requestId | String | 请求ID。 |
| success | Boolean | 是否成功。 |
| content | Array | 返回内容。 |
| OpenAgoalKeyActionDTO | OpenAgoalKeyActionDTO | 关联的关键结果对象。 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/agoal/objectives/keyActionLists?objectiveId=6444f5e9a4261c6e699dxxxx&keyResultId=6444f5e9a4261c6e699dxxxx&dingUserId=211042291978xxxx HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:39efe7f73ee236ec88972fe18f7bxxxx
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
    "keyActionId" : "6444f5e9a4261c6e699dxxxx",
    "title" : "测试",
    "url" : "https://agoal.dingtalk.com"
  } ]
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 500 | error.systemError | 系统异常 | 系统异常 |
| 500 | error.noPermission | 无权限 | 无权限 |