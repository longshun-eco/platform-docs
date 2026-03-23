---
title: "获取应用的 Access Token新版SDK"
source: "https://open.dingtalk.com/document/development/api-gettoken"
category: "服务端API / 获取访问凭证 / 获取应用身份相关访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-gettoken_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-gettoken_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-23如果你的应用需要使用应用权限点，无论是企业内部应用还是第三方企业应用，都应通过本接口获取应用级别的 Access Token。该凭证用于调用钉钉开放平台中受权限保护的 API 接口。

## 使用场景

此接口用于获取企业内部应用或第三方企业应用调用API所需的Access Token，适用于所有需要通过应用身份鉴权调用钉钉开放平台接口的场景。

## **调用说明**

如果你之前使用：

* 企业内部应用：调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口，获取企业调用接口的凭证信息。
* 第三方企业应用：调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口，获取第三方应用授权企业调用接口的凭证信息。

现在这两种场景统一为一个接口，无需区分应用类型，直接调用本接口即可获取 AccessToken 调用应用权限接口。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 无需申请 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=oauth2_1.0%23GetToken) |
| 第三方企业应用 | 支持 | 无需申请 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=oauth2_1.0%23GetToken) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/oauth2/{corpId}/token HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "client_id" : "ding123",
  "client_secret" : "*******",
  "grant_type" : "client_credentials"
}
```

## Path参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| corpId | String | 是 | 组织ID，应用运行在哪个组织就填写哪个组织的 corpId：   * 企业内部应用：填写本企业 corpId。 * 第三方企业应用：填写开通应用的授权企业的 corpId。 |

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| client\_id | String | 是 | 应用的 ClientID。 |
| client\_secret | String | 是 | 应用的 ClientSecret。 |
| grant\_type | String | 是 | 授权类型：   * client\_credentials |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| access\_token | String | 访问凭证。 |
| expires\_in | Integer | 访问凭证有效的时长，单位秒。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/oauth2/ding9f****41/token HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "client_id" : "suite123",
  "client_secret" : "********",
  "grant_type" : "client_credentials"
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
  "access_token" : "2bf******9be361a5084f1e2b8",
  "expires_in" : 7200
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalid.client | invalid.client | 无效的ClientID或ClientSecret |
| 400 | unsupported.grant.type | unsupported.grant.type | 不支持此授权类型，请检查授权类型参数 |
| 401 | unauthorized.client | unauthorized.client | 应用未被授权 |
| 500 | server.error | server.error | 服务器意外错误 |