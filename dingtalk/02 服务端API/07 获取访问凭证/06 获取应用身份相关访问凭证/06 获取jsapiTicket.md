---
title: "获取jsapiTicket新版SDK"
source: "https://open.dingtalk.com/document/development/create-a-jsapi-ticket"
category: "服务端API / 获取访问凭证 / 获取应用身份相关访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-create-a-jsapi-ticket_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-create-a-jsapi-ticket_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-11当开发H5微应用时，需要先通过本接口获取jsapi\_ticket，然后再生成鉴权签名，最后调用dd.config完成鉴权。

**说明**

企业内部应用是以应用维度获取jsapi\_ticket的，所以在使用的时候需要将jsapi\_ticket以appKey为维度进行缓存下来（设置缓存过期时间2小时），并不需要每次都通过接口拉取。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 调用企业API基础权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=oauth2_1.0%23CreateJsapiTicket) |
| 第三方企业应用 | 支持 | 调用企业API基础权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=oauth2_1.0%23CreateJsapiTicket) |
| 第三方个人应用 | 暂不支持 | 调用企业API基础权限 | 暂不支持 |

## 请求方法

```
POST /v1.0/oauth2/jsapiTickets HTTP/1.1
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
| jsapiTicket | String | 返回的jsapi\_ticket。 |
| expireIn | Long | jsapiTicket过期时间，单位秒。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/oauth2/jsapiTickets HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:BExxx
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
  "jsapiTicket" : "asjdgxxx",
  "expireIn" : 7200
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalidClientIdOrSecret | 无效的clientId或者clientSecret | 无效的clientId或者clientSecret |
| 500 | systemBusy | 系统繁忙 | 系统繁忙 |