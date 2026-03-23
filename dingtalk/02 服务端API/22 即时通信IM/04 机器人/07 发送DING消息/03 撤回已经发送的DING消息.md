---
title: "撤回已经发送的DING消息专业版去升级新版SDK"
source: "https://open.dingtalk.com/document/development/robot-withdraws-pin-message"
category: "服务端API / 即时通信IM / 机器人 / 发送DING消息"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-robot-withdraws-pin-message_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-robot-withdraws-pin-message_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-12

**接口调用量说明**当前接口为钉钉专业版和[钉钉专属版](https://partner.dingtalk.com/opportunity_web.html?channel=openpf_web_devdoc_apiDING_trial&templateId=092b3722b3fd4dd08fb641a194a90691#/consultingService)专享接口，仅限钉钉专业版和钉钉专属版客户使用，并可按需[增购OpenAPI发DING额度](https://oa.dingtalk.com/index.htm#/dataCenter/dingOrder?_dlp_=channel%3Dopenpf_web_devdoc_apiDING)

调用本接口，可撤回使用企业机器人发送的DING消息。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 企业机器人发送撤回DING消息 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=robot_1.0%23RobotRecallDing) |
| 第三方企业应用 | 暂不支持 | 企业机器人发送撤回DING消息 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 企业机器人发送撤回DING消息 | 暂不支持 |

## 请求方法

```
POST /v1.0/robot/ding/recall HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "robotCode" : "String",
  "openDingId" : "String"
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
| robotCode | String | 是 | 发送DING消息的机器人ID。  **说明**  需要撤销的DING消息，发送和撤回操作必须是同一个机器人。 |
| openDingId | String | 是 | 需要被撤回的DING消息ID，可调用[发送DING消息](/document/development/robot-sends-nail-message)接口获取。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| openDingId | String | 撤回成功的DING消息ID。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/robot/ding/recall HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:xxxxx
Content-Type:application/json

{
  "robotCode" : "dingxxxxxxxxx",
  "openDingId" : "54165xxx"
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
  "openDingId" : "54165xxx"
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | recall.ding.exception | recall.ding.exception %s | 撤回DING消息异常 |
| 400 | invalidParameter.param.invalid | 参数不合法%s | 参数不合法 |
| 500 | system.error | system.error | 系统异常 |