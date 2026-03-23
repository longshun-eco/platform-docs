---
title: "获取用户token新版SDK"
source: "https://open.dingtalk.com/document/development/obtain-user-token"
category: "服务端API / 获取访问凭证 / 获取用户个人身份访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-user-token_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-user-token_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22通过此接口获取用户级别的访问令牌（access token），支持 OAuth 2.0 授权码模式和刷新令牌模式，适用于需要以用户身份调用钉钉开放平台 API 的第三方个人应用。

## 使用场景

该接口用于获取用户的`accessToken`，是实现用户身份认证的关键步骤。常见使用场景包括：

* 用户登录后，通过授权码（`code`）换取有效的访问凭证。
* 在`accessToken`过期前，使用`refreshToken`自动续期，避免频繁重新授权。
* 第三方企业应用集成钉钉统一登录体系，实现单点登录（SSO）。
* 企业应用在后台服务中代表用户调用受保护的 API 接口。

开发者应妥善管理`accessToken`的生命周期，建议在本地缓存并设置自动刷新机制，确保调用稳定性。

**说明**

在使用accessToken时，请注意：

* `accessToken`的有效期为7200秒（2小时），有效期内重复获取将返回相同结果并自动续期；过期后获取会返回新的`accessToken`。
* 每个应用的`accessToken`相互独立，缓存时需按应用维度进行存储，防止混淆。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 默认开通 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=oauth2_1.0%23GetUserToken) |
| 第三方企业应用 | 支持 | 默认开通 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=oauth2_1.0%23GetUserToken) |
| 第三方个人应用 | 支持 | 默认开通 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=personal&api=oauth2_1.0%23GetUserToken) |

## 请求方法

```
POST /v1.0/oauth2/userAccessToken HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "clientId" : "String",
  "clientSecret" : "String",
  "code" : "String",
  "refreshToken" : "String",
  "grantType" : "String"
}
```

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| clientId | String | 是 | 应用id。可使用扫码登录应用或者第三方个人小程序的appId。   * 企业内部应用传应用的**AppKey** * 第三方企业应用传应用的**SuiteKey** * 第三方个人应用传应用的**AppId** |
| clientSecret | String | 是 | 应用密钥。   * 企业内部应用传应用的**AppSecret** * 第三方企业应用传应用的**SuiteSecret** * 第三方个人应用传应用的**AppSecret** |
| code | String | 否 | OAuth 2.0 临时授权码，第三方企业应用需要[接入统一授权套件](/document/development/unified-licensing-suite-sdk)/[获取登录用户的访问凭证](/document/development/obtain-identity-credentials)，获取临时授权码authCode。 |
| refreshToken | String | 否 | OAuth 2.0 刷新令牌，从上一次接口返回结果中获取。有效期为 30 天。 |
| grantType | String | 是 | * 如果使用授权码换token：传`authorization_code`，此时必须填写`code`参数。 * 使用刷新 token 换新 token：传`refresh_token`，此时必须填写`refreshToken`参数。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| accessToken | String | 生成的accessToken，用于后续 API 调用的身份验证。 |
| refreshToken | String | 生成的refresh\_token。可以使用此刷新token，定期的获取用户的accessToken |
| expireIn | Long | 超时时间，单位秒。 |
| corpId | String | 所选企业corpId。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/oauth2/userAccessToken HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "clientId" : "dingxxx",
  "clientSecret" : "1234",
  "code" : "abcd",
  "refreshToken" : "abcd",
  "grantType" : "authorization_code"
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
  "accessToken" : "abcd",
  "refreshToken" : "abcd",
  "expireIn" : 7200,
  "corpId" : "corpxxxx"
}
```