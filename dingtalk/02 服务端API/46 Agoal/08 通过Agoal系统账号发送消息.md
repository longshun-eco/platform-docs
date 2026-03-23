---
title: "通过Agoal系统账号发送消息新版SDK"
source: "https://open.dingtalk.com/document/development/api-agoalsendmessage"
category: "服务端API / Agoal"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-agoalsendmessage_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-agoalsendmessage_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-06调用本接口通过Agoal助手系统账号发送消息卡片，需要传入模板id、参数、发送人、接收人等信息，返回值为消息发送成功与否。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | Agoal消息发送权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=agoal_1.0%23AgoalSendMessage) |
| 第三方企业应用 | 支持 | Agoal消息发送权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=agoal_1.0%23AgoalSendMessage) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/agoal/messages/send HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "templateId" : "String",
  "params" : "String",
  "mobileUrl" : "String",
  "pcUrl" : "String",
  "sourceDingUserId" : "String",
  "targetDingUserIds" : [ "String" ]
}
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| templateId | String | 是 | 消息模板id。 |
| params | String | 是 | 模板参数。 |
| mobileUrl | String | 是 | 移动端链接。 |
| pcUrl | String | 是 | PC端链接。 |
| sourceDingUserId | String | 是 | 发送人dingUserId。 |
| targetDingUserIds | Array of String | 是 | 接收人dingUserId。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| requestId | String | 请求ID。 |
| success | Boolean | 接口调用是否成功。 |
| content | Boolean | 返回结果，消息是否发送成功。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/agoal/messages/send HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:9801a354e3d03539baa83e5f275axxxx
Content-Type:application/json

{
  "templateId" : "1d01a14febc7482ca3b6e1d30cf5xxxx",
  "params" : "{\"A\":\"a\", \"B\":\"b\"}",
  "mobileUrl" : "https://agoal.dingtalk.com",
  "pcUrl" : "https://agoal.dingtalk.com",
  "sourceDingUserId" : "211042291978xxxx",
  "targetDingUserIds" : [ "211042291978xxxx" ]
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
  "requestId" : "7478B23C-80E8-1AD6-BE8C-09D480E0xxxx",
  "success" : true,
  "content" : true
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 500 | error.systemError | 系统异常 | 系统异常 |
| 500 | error.noPermission | 无权限 | 无权限 |