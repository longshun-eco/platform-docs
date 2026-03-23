---
title: "DING服务新版SDK"
source: "https://open.dingtalk.com/document/development/send-in-application-ding"
category: "服务端API / 专属钉钉 / DING"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-send-in-application-ding_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-send-in-application-ding_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23调用本接口通过专属DING服务中设置的互动服务窗来发送应用内DING。

**说明**

* 该文档将不再维护，如需使用请使用[发送DING消息](/document/development/robot-sends-nail-message)新接口。
* 专属钉钉API接口仅针对专属钉钉客户开放，专属钉钉简介和本文档中API使用问题咨询请[查看专属钉钉说明](https://oa.dingtalk.com/register_new.htm?spm=ding_open_doc.document.0.0.20851fcacmWWQT&source=50061&useMt2=1#/)。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 专属钉钉发DING权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=exclusive_1.0%23SendAppDing) |
| 第三方企业应用 | 暂不支持 | 暂不支持 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/exclusive/appDings/send HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "userids" : [ "String" ],
  "content" : "String"
}
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 |

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| userids | Array of String | 是 | 接收DING消息的用户userid列表。 |
| content | String | 是 | 消息内容。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/exclusive/appDings/send HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:BExxx
Content-Type:application/json

{
  "userids" : [ "123" ],
  "content" : "开会"
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
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | assign.lack | 管理员未签署协议 | 管理员未签署协议 |
| 400 | volume.lack | 额度不足 | 额度不足 |
| 400 | message.duplicate | 重复内容，发送失败 | 重复内容，发送失败 |
| 400 | param.illegal | 参数不合法 | 参数不合法 |
| 400 | publisher.notexist | 服务号不存在 | 服务号不存在 |
| 500 | system.error | 系统内部错误 | 系统内部错误 |