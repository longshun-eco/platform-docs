---
title: "获取Agoal用户管理员列表新版SDK"
source: "https://open.dingtalk.com/document/development/api-agoaluseradminlist"
category: "服务端API / Agoal"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-agoaluseradminlist_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-agoaluseradminlist_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-06调用本接口获取Agoal用户管理列表，返回信息包括用户的dingUserId和请求的钉钉corpId，数组形式返回。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | Agoal用户管理员读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=agoal_1.0%23AgoalUserAdminList) |
| 第三方企业应用 | 支持 | Agoal用户管理员读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=agoal_1.0%23AgoalUserAdminList) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
GET /v1.0/agoal/administrators/lists HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| requestId | String | 请求ID。 |
| success | Boolean | 请求是否成功。 |
| content | Array | 返回结果，管理员列表。 |
| OpenUserAdminDTO | OpenUserAdminDTO | 用户管理员对象。 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/agoal/administrators/lists HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:bef2c8xxx
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
    "dingCorpId" : "dingxxxxe3d8c283bb4aa39a90f97fcb1e09",
    "dingUserId" : "211042291978xxxx"
  } ]
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 500 | error.systemError | 系统异常 | 系统异常 |
| 500 | error.noPermission | 无权限 | 无权限 |