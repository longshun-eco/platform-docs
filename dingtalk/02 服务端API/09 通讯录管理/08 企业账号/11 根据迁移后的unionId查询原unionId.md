---
title: "根据迁移后的unionId查询原unionId新版SDK"
source: "https://open.dingtalk.com/document/development/query-the-original-union-id-based-on-the-union-id"
category: "服务端API / 通讯录管理 / 企业账号"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-query-the-original-union-id-based-on-the-union-id_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-query-the-original-union-id-based-on-the-union-id_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-11调用本接口，根据迁移后的unionId查询原unionId。

### 接口功能介绍

普通账号迁移为企业账号后，可调用本接口根据迁移后企业账号的unionId查询原普通账号的unionId。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 通讯录企业账号迁移数据读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=contact_1.0%23GetUnionIdByMigrationUnionId) |
| 第三方企业应用 | 支持 | 通讯录企业账号迁移数据读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=contact_1.0%23GetUnionIdByMigrationUnionId) |
| 第三方个人应用 | 暂不支持 | 通讯录企业账号迁移数据读权限 | 暂不支持 |

## 请求方法

```
GET /v1.0/contact/orgAccount/getUnionIdByMigrationUnionIds?migrationUnionId=String HTTP/1.1
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
| migrationUnionId | String | 是 | 迁移后企业账号的unionId，可调用[查询企业账号用户详情](/document/development/queries-the-details-of-a-dedicated-account)接口获得unionid参数值。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| unionId | String | 原普通账号的unionId。 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/contact/orgAccount/getUnionIdByMigrationUnionIds?migrationUnionId=yyyy HTTP/1.1
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

C++

```
// This file is auto-generated, don't edit it. Thanks.
```

**返回示例**

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "unionId" : "zzzz"
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalid.param | 无效参数 | 无效参数 |
| 400 | invalid.userid | 找不到该用户 | 找不到该用户 |
| 400 | illegal.migration.unionId | 非法的migrationUnionId | 非法的migrationUnionId |
| 500 | system.busy | 系统繁忙 | 系统繁忙 |