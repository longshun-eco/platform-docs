---
title: "获取 dentryUuid 信息"
source: "https://open.dingtalk.com/document/development/api-getuuidbydentryid"
category: "服务端API / 文档/文件 / 存储管理 / 文件管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-getuuidbydentryid_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-getuuidbydentryid_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-03-19根据文件的 spaceId 和 dentryId 获取文件的 dentryUuid 信息。

## 权限

要调用此API，需要以下权限之一。

| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| --- | --- | --- | --- |
| 企业内部应用 | 支持 | 知识库文档读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=doc_2.0%23GetUuidByDentryId) |
| 第三方企业应用 | 支持 | 知识库文档读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=doc_2.0%23GetUuidByDentryId) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
GET /v2.0/doc/dentries/{dentryId}/queryDentryUuid?spaceId=String&operatorId=String HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用可调用[获取企业内部应用的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用可调用[获取第三方应用授权企业的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Path参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| dentryId | String | 是 | 当前文件的 ID。 |

## Query参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| spaceId | String | 是 | 空间 ID。 |
| operatorId | String | 是 | 操作人 unionId，调用[查询用户详情](https://open.dingtalk.com/document/development/query-user-details)接口获取 unionid 参数值。 |

## 返回参数

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| dentryUuid | String | 当前文件 UUID。 |
| dentryId | String | 当前文件 ID。 |
| spaceId | String | 当前空间 ID。 |

## 示例

**请求示例**

HTTP

```
GET /v2.0/doc/dentries/1744xxxx000/queryDentryUuid?spaceId=490xxxx76&operatorId=E9CS6xxxxN7QiEiE HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:873d8xxxx9380ad
Content-Type:application/json
```

Java

```go
package com.aliyun.sample;
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

```go
package main
```

Node.js

```
'use strict';
```

C#

```
using Newtonsoft.Json;
```

**返回示例**

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "dentryUuid" : "Qnp9zOxxxx1DK0g6l",
  "dentryId" : "1744xxxx2000",
  "spaceId" : "490xxxx976"
}
```

## 错误码

| HttpCode | 错误码 | 错误信息 | 说明 |
| --- | --- | --- | --- |
| 400 | paramError | %s | 参数错误 |
| 403 | permissionDenied | The operator has no permission. | 当前用户无此操作权限 |
| 404 | documentNotExist | %s | 文档不存在或格式不支持 |
| 500 | systemError | %s | 服务繁忙，请稍后重试 |
| 500 | unknownError | Unknown Error | 未知错误 |