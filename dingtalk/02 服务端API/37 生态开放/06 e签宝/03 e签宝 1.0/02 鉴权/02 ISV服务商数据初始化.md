---
title: "ISV服务商数据初始化新版SDK"
source: "https://open.dingtalk.com/document/development/offline-isv-service-provider-data-initialization"
category: "服务端API / 生态开放 / e签宝 / e签宝 1.0 / 鉴权"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-offline-isv-service-provider-data-initialization_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-offline-isv-service-provider-data-initialization_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23调用本接口帮助钉钉ISV服务商进行e签宝开放平台的数据初始化。所有e签宝接口在调用前，都需要成为e签宝的开发者，基于ISV服务商数据已完成初始化。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 暂不支持 | E签宝数据管理权限 | 暂不支持 |
| 第三方企业应用 | 支持 | E签宝数据管理权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=esign_1.0%23CreateDeveloper) |
| 第三方个人应用 | 暂不支持 | E签宝数据管理权限 | 暂不支持 |

## 请求方法

```
GET /v1.0/esign/developers/create HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "redirectUrl" : "String"
}
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| redirectUrl | String | 否 | 通知回调地址。  **说明**  目前需要手动传入。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| code | Integer | 返回码。 |
| message | String | 返回码描述。 |
| data | Boolean | 数据初始化结果：   * **true**：成功 * **false**：失败 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/esign/developers/create HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:BE3xxxx
Content-Type:application/json

{
  "redirectUrl" : "http://ddxxxx.com"
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
  "code" : 0,
  "message" : "成功",
  "data" : true
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalidRequest.invalidAguemnts | invalid arguments | 参数错误 |