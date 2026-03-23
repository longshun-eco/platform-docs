---
title: "获取第三方企业应用的suiteAccessToken新版SDK"
source: "https://open.dingtalk.com/document/development/obtains-the-suite-acess-token-of-third-party-enterprise-applications"
category: "服务端API / 获取访问凭证 / 获取应用身份相关访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtains-the-suite-acess-token-of-third-party-enterprise-applications_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtains-the-suite-acess-token-of-third-party-enterprise-applications_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-11调用本接口获取第三方企业应用的suiteAccessToken。

该suiteAccessToken主要用于获取第三方企业应用的信息，在调用以下接口时会使用第三方企业应用的suiteAccessToken：

* [获取授权应用的基本信息](/document/development/obtains-application-information-of-an-enterprise)
* [获取企业授权信息](/document/development/obtains-the-basic-information-of-an-enterprise)

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 暂不支持 | 无需申请 | 暂不支持 |
| 第三方企业应用 | 支持 | 无需申请 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=oauth2_1.0%23GetSuiteAccessToken) |
| 第三方个人应用 | 暂不支持 | 无需申请 | 暂不支持 |

## 请求方法

```
POST /v1.0/oauth2/suiteAccessToken HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "suiteKey" : "String",
  "suiteSecret" : "String",
  "suiteTicket" : "String"
}
```

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| suiteKey | String | 是 | 已创建的第三方企业应用的 Cilent ID（原第三方企业应用SuiteKey）。 |
| suiteSecret | String | 是 | 已创建的第三方企业应用的 Cilent Secret（原第三方企业应用SuiteSecret）。 |
| suiteTicket | String | 是 | 钉钉开放平台会向应用的回调URL推送的suite\_ticket（约5个小时推送一次），详细内容请参考[套件票据](/document/development/event-suite-ticket)。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| accessToken | String | 第三方企业应用的凭证。 |
| expireIn | Long | 第三方企业应用的凭证过期时间，单位秒。  **说明**  suiteAccessToken有效期为7200秒，过期之前建议服务端做定时器主动更新，而不是依赖钉钉的定时推送。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/oauth2/suiteAccessToken HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "suiteKey" : "suitefcurkdvkc1nxxxx",
  "suiteSecret" : "y1ie2Rfb54xxxx",
  "suiteTicket" : "test"
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
  "accessToken" : "token",
  "expireIn" : 7200
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalidSuiteTicket | suiteTicket无效 | suiteTicket无效 |
| 400 | invalidClientIdOrSecret | clientId或者clientSecret错误 | clientId或者clientSecret错误 |