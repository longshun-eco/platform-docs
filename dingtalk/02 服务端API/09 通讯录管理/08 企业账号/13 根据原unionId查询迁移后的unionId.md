---
title: "根据原unionId查询迁移后的unionId新版SDK"
source: "https://open.dingtalk.com/document/development/the-union-id-that-you-want-to-query-you-can"
category: "服务端API / 通讯录管理 / 企业账号"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-the-union-id-that-you-want-to-query-you-can_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-the-union-id-that-you-want-to-query-you-can_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-11调用本接口，根据原unionId查询迁移后的unionId。

### 接口功能说明

普通账号迁移为企业账号后，可调用本接口根据原普通账号的unionId查询迁移后企业账号的unionId。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 通讯录企业账号迁移数据读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=contact_1.0%23GetMigrationUnionIdByUnionId) |
| 第三方企业应用 | 支持 | 通讯录企业账号迁移数据读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=contact_1.0%23GetMigrationUnionIdByUnionId) |
| 第三方个人应用 | 暂不支持 | 通讯录企业账号迁移数据读权限 | 暂不支持 |

## 请求方法

```
GET /v1.0/contact/orgAccount/getMigrationUnionIdByUnionIds?unionId=String HTTP/1.1
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
| unionId | String | 是 | 原普通账号的unionId，可调用[通过免登码获取用户信息](/document/development/obtain-the-userid-of-a-user-by-using-the-log-free)获取unionid参数值。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| migrationUnionIdList | Map | 迁移后企业账号的unionId。 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/contact/orgAccount/getMigrationUnionIdByUnionIds?unionId=yyyy HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:BExxxx
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
  "$:LWCP_v1" : "$zzz"
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalid.param | 入参不能为空 | 入参不能为空 |
| 400 | invalid.unionId | 入参unionId不能为空 | 入参unionId不能为空 |
| 500 | system.busy | 系统繁忙 | 系统繁忙 |