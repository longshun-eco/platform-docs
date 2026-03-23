---
title: "获取微应用后台免登的accessToken新版SDK"
source: "https://open.dingtalk.com/document/development/obtain-the-access-token-of-the-micro-application-background-without-log-on"
category: "服务端API / 获取访问凭证 / 获取应用身份相关访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-the-access-token-of-the-micro-application-background-without-log-on_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-the-access-token-of-the-micro-application-background-without-log-on_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-11调用本接口获取微应用后台免登的accessToken。获取的accessToken只在应用管理后台免登场景中使用。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 调用企业API基础权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=oauth2_1.0%23GetSsoAccessToken) |
| 第三方企业应用 | 支持 | 调用企业API基础权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=oauth2_1.0%23GetSsoAccessToken) |
| 第三方个人应用 | 暂不支持 | 调用企业API基础权限 | 暂不支持 |

## 请求方法

```
POST /v1.0/oauth2/ssoAccessToken HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "corpid" : "String",
  "ssoSecret" : "String"
}
```

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| corpid | String | 是 | 企业的corpId。 |
| ssoSecret | String | 是 | sso密钥，可以在[开发者后台](https://open-dev.dingtalk.com/fe/old#/corpAuthInfo)**基本信息**—**开发信息**（**旧版**）页面查看。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| accessToken | String | 微应用后台免登的accessToken。 |
| expireIn | Long | 超时时间。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/oauth2/ssoAccessToken HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "corpid" : "corpxxxx",
  "ssoSecret" : "shYgsk7xxx"
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
  "accessToken" : "1234",
  "expireIn" : 3600
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalidClientIdOrSecret | 无效的clientId或者clientSecret | 无效的clientId或者clientSecret |