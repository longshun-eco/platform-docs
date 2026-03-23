---
title: "发送Rooms中控API信令新版SDK"
source: "https://open.dingtalk.com/document/development/api-sendcentralcontrol"
category: "服务端API / 音视频 / 智能会议室 / 会议室"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-sendcentralcontrol_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-sendcentralcontrol_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-25给会议室中的设备发送中控信令，属于高级功能。

## 权限

要调用此API，需要以下权限之一。

| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| --- | --- | --- | --- |
| 企业内部应用 | 支持 | 视频会议信息管理权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=rooms_1.0%23SendCentralControl) |
| 第三方企业应用 | 暂不支持 | 暂不支持 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/rooms/central/control HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "unionId" : "String",
  "roomId" : "String",
  "controlBody" : "String"
}
```

## Header参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，可调用[获取企业内部应用的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 |

## Body参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| unionId | String | 否 | 操作人unionId，可调用[查询用户详情](https://open.dingtalk.com/document/development/query-user-details)接口获取。 |
| roomId | String | 否 | 会议室ID，可通过调用[查询会议室列表](https://open.dingtalk.com/document/development/check-the-meeting-room-list) 接口获取。 |
| controlBody | String | 否 | 中控信令。  **说明**  该参数请联系对应的客户经理获取。 |

## 返回参数

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| result | Boolean | 接口调用是否成功。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/rooms/central/control HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:2WCDFxxxxx
Content-Type:application/json

{
  "unionId" : "2iPOLbpUNMLzB5LuwggiiqiPwiEiE",
  "roomId" : "0ffb7xxxxx",
  "controlBody" : "{   \"version\": \"1.0.0\",    \"request\": {     \"requestId\": \"xxxx\",      \"service\": \"DTRooms.Meeting\",      \"method\": \"subscribe\"    } }"
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
  "result" : true
}
```

## 错误码

| HttpCode | 错误码 | 错误信息 | 说明 |
| --- | --- | --- | --- |
| 400 | param.error | Param Error | 参数缺失错误 |
| 400 | user.not.org | User Not In Org | 用户不在组织内 |
| 400 | api.control.close | API CONTROL ClOSE | 会议室未开启中控能力 |
| 500 | system.error | System Error | 系统错误 |