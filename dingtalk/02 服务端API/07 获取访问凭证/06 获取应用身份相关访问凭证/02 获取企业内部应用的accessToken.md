---
title: "获取企业内部应用的accessToken新版SDK"
source: "https://open.dingtalk.com/document/development/obtain-the-access-token-of-an-internal-app"
category: "服务端API / 获取访问凭证 / 获取应用身份相关访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-the-access-token-of-an-internal-app_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-the-access-token-of-an-internal-app_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-23企业内部应用调用本接口获取访问凭证（accessToken）。在调用钉钉服务端API时，需通过accessToken进行身份鉴权，以确保请求来源合法并具备相应权限。

## **使用场景**

本接口适用于企业内部系统集成场景，用于获取调用钉钉开放能力所需的访问凭证。典型使用流程如下：

* 应用启动或首次调用API前，调用本接口获取accessToken。
* 将获取到的accessToken缓存至本地存储（如Redis、内存缓存等），避免重复请求。
* 后续所有依赖鉴权的API调用均携带该accessToken。
* 建议设置缓存过期时间略小于7200秒（例如7000秒），实现自动刷新机制，防止因时间偏差导致凭证失效。
* 注意避免在短时间内频繁调用本接口，否则可能触发频率限制策略，影响服务稳定性。

## **获取Client ID与Client Secret**

在调用接口前，需先在开发者后台获取对应的企业内部应用凭证信息：

1. 登录钉钉[开发者后台](https://open-dev.dingtalk.com/)。
2. 在**应用开发**页面，单击目标应用进入应用详情页。
3. 进入**基础信息 > 凭证与基础信息**页面。
4. 复制应用的 Client ID（原企业内部应用AppKey）和 Client Secret（原企业内部应用AppSecret）。

   > **提示**：请妥善保管Client Secret，避免泄露。

   ![[development-obtain-the-access-token-of-an-internal-app_p953842.png]]

**说明**

在使用accessToken时，请注意以下几点：

* accessToken的有效期为7200秒（2小时），有效期内重复获取会返回相同结果并自动续期，过期后获取会返回新的accessToken。
* 开发者应自行缓存accessToken，并根据应用维度进行区分存储，因为每个企业内部应用的accessToken相互独立。
* 不可频繁调用本接口获取凭证，建议结合缓存机制控制调用频次，防止被系统限流。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 默认开通，无需申请 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=oauth2_1.0%23GetAccessToken) |
| 第三方企业应用 | 暂不支持 | 默认开通，无需申请 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 默认开通，无需申请 | 暂不支持 |

## 请求方法

```
POST /v1.0/oauth2/accessToken HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "appKey" : "String",
  "appSecret" : "String"
}
```

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| appKey | String | 是 | 已创建的企业内部应用的 Cilent ID（原企业内部应用AppKey）。 |
| appSecret | String | 是 | 已创建的企业内部应用的 Cilent Secre （原企业内部应用AppSecret）。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| accessToken | String | 生成的accessToken。 |
| expireIn | Long | accessToken的过期时间，单位秒。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/oauth2/accessToken HTTP/1.1
Host:api.dingtalk.com
Content-Type:application/json

{
  "appKey" : "dingeqqpkv3xxxxxx",
  "appSecret" : "GT-lsu-taDAxxxsTsxxxx"
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

python2

```
# -*- coding: utf-8 -*-
```

Swift

```
#!/usr/bin/env xcrun swift
```

**返回示例**

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "accessToken" : "fw8ef8we8f76e6f7s8dxxxx",
  "expireIn" : 7200
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalidClientIdOrSecret | 无效的clientId或者clientSecret | 无效的clientId或者clientSecret |