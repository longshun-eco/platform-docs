---
title: "获取群会话的OpenConversationId新版SDK"
source: "https://open.dingtalk.com/document/development/obtain-group-openconversationid"
category: "服务端API / 即时通信IM / 会话管理 / 会话 v1.0（群管理）"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-group-openconversationid_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-group-openconversationid_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-12调用本接口，通过chatId查询OpenConversationId。

本接口适用于在创建群会话时未保存 OpenConversationId，后续业务需要使用该 ID 的场景。

**说明**

如果在调用[创建群](/document/development/create-group-session)接口时没有保存OpenConversationId，可以通过调用本接口通过chatId获取OpenConversationId。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 钉钉群基础信息读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=im_1.0%23ChatIdToOpenConversationId) |
| 第三方企业应用 | 暂不支持 | 暂不支持 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/im/chat/{chatId}/convertToOpenConversationId HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 |

## Path参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| chatId | String | 是 | 群会话chatId，可通过[创建群](/document/development/create-group-session)接口获取chatId参数值。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| openConversationId | String | 群会话openConversationId。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/im/chat/chatfaabe59a460527f5fb72fbbdfe3f061e/convertToOpenConversationId HTTP/1.1
Host:api.dingtalk.com
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

C++

```
// This file is auto-generated, don't edit it. Thanks.
```

**返回示例**

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "openConversationId" : "cidl1B8RVUFmkO50OC9uEbySQ=="
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | invalideChatId | 不合法的chatId | 不合法的chatId |