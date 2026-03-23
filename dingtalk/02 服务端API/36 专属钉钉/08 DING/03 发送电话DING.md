---
title: "发送电话DING新版SDK"
source: "https://open.dingtalk.com/document/development/outgoing-phone-ding"
category: "服务端API / 专属钉钉 / DING"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-outgoing-phone-ding_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-outgoing-phone-ding_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23调用本接口，可以通过互动服务窗的服务号发送电话DING。

### 接口调用流程

调用本接口发送电话DING消息，需要完成以下配置，步骤如下：

步骤一：登录[钉钉管理后台](https://oa.dingtalk.com)。

步骤二：在**钉钉管理后台**页面，依次单击**专属钉钉 > 专属开放 > DING服务 > 电话DING容量**，完成如下图所示配置。

![[development-outgoing-phone-ding_O1CN01JOFadM1RcVBjPhkOU_!!6000000002132-2-tps-2526-1260.png]]

**说明**

DING电话推送号，需要先在当前组织内的**互动服务窗**应用中添加，如下图所示。添加完成后，再去**钉钉管理后台**的**电话DING容量**页面配置。

![[development-outgoing-phone-ding_O1CN01g5dsIh1hc4fdLy2KI_!!6000000004297-2-tps-2624-1120.png]]

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 专属钉钉发电话DING权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=exclusive_1.0%23SendPhoneDing) |
| 第三方企业应用 | 暂不支持 | 专属钉钉发电话DING权限 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 专属钉钉发电话DING权限 | 暂不支持 |

## 请求方法

```
POST /v1.0/exclusive/phoneDings/send HTTP/1.1
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
| userids | Array of String | 是 | 接收DING消息的用户userId列表，最大值20。 |
| content | String | 是 | 消息内容。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| success | Boolean | 发送Ding消息是否成功。   * **true**：成功 * **false**：失败 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/exclusive/phoneDings/send HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:xxxxx
Content-Type:application/json

{
  "userids" : [ "user123" ],
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
  "success" : true
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | assign.lack | 管理员未签署协议 | 管理员未签署协议 |
| 400 | message.duplicate | 重复内容，发送失败 | 重复内容，发送失败 |
| 400 | param.illegal | 参数不合法 | 参数不合法 |
| 400 | publisher.notexist | 服务号不存在 | 服务号不存在 |
| 400 | volume.lack | 电话DING额度不足 | 电话DING额度不足 |
| 400 | batch.toolarge | 每批接受人数超20 | 每批接受人数超20 |
| 400 | phoneding.reachlimit | 电话DING发送已达上限 | 电话DING发送已达上限 |
| 400 | send.toofast | 发送频繁，请稍后再试 | 发送频繁，请稍后再试 |