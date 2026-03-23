---
title: "获取定制应用的accessToken新版SDK"
source: "https://open.dingtalk.com/document/development/obtain-the-access-token-of-the-third-party-application-authorization-enterprise"
category: "服务端API / 获取访问凭证 / 获取应用身份相关访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-the-access-token-of-the-third-party-application-authorization-enterprise_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-the-access-token-of-the-third-party-application-authorization-enterprise_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22产品服务商可通过此接口获取授权企业的accessToken。定制应用调用服务端API获取应用资源时，使用获取的accessToken进行身份验证。

**说明**

在使用accessToken时，请注意：

* accessToken的有效期为7200秒（2小时），有效期内重复获取会返回新的accessToken。
* 开发者需要缓存accessToken，用于后续接口的调用。因为每个应用的accessToken是彼此独立的，所以进行缓存时需要区分应用来进行存储。
* 不能频繁调用gettoken接口，否则会受到频率拦截。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用（委托产品服务商开发时使用） | 支持 | 默认开通，无需申请 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=oauth2_1.0%23GetCorpAccessToken) |
| 第三方企业应用 | 支持 | 默认开通，无需申请 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=oauth2_1.0%23GetCorpAccessToken) |
| 第三方个人应用 | 暂不支持 | 默认开通，无需申请 | 暂不支持 |

## 请求方法

```
POST /v1.0/oauth2/corpAccessToken HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "suiteKey" : "String",
  "suiteSecret" : "String",
  "authCorpId" : "String",
  "suiteTicket" : "String"
}
```

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| suiteKey | String | 是 | 定制应用的CustomKey。 |
| suiteSecret | String | 是 | 定制应用的CustomSecret。 |
| authCorpId | String | 是 | 授权企业的CorpId。 ![[development-obtain-the-access-token-of-the-third-party-application-authorization-enterprise_p504856.png]] |
| suiteTicket | String | 是 | 钉钉推送的suiteTicket，定制应用该参数自定义，比如Test。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| accessToken | String | 定制应用的的accessToken。 |
| expireIn | Long | 定制应用的accessToken超时时间，单位秒。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/oauth2/corpAccessToken HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:1cc1bb3xxxx
Content-Type:application/json

{
  "suiteKey" : "suitep1f5lzyglm7fryxxxx",
  "suiteSecret" : "_FP5PpZF3irDKjxxx",
  "authCorpId" : "ding123456",
  "suiteTicket" : "1f5lzyglm7fryxxxx"
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

**返回示例**

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "accessToken" : "1cc1bb3xxxx",
  "expireIn" : 7200
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalidSuiteKey | suitekey不合法 | suitekey不合法 |
| 400 | invalidSuiteTicket | suiteTicket无效 | suiteTicket无效 |
| 400 | invalidAuthInfo | 授权关系不存在 | 企业未开通对应的三方应用，无法获取该企业token |