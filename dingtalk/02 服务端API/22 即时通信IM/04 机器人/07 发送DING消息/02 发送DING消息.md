---
title: "发送DING消息专业版去升级新版SDK"
source: "https://open.dingtalk.com/document/development/robot-sends-nail-message"
category: "服务端API / 即时通信IM / 机器人 / 发送DING消息"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-robot-sends-nail-message_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-robot-sends-nail-message_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23

**接口调用量说明**当前接口为钉钉专业版和[钉钉专属版](https://partner.dingtalk.com/opportunity_web.html?channel=openpf_web_devdoc_apiDING_trial&templateId=092b3722b3fd4dd08fb641a194a90691#/consultingService)专享接口，仅限钉钉专业版和钉钉专属版客户使用，并可按需[增购OpenAPI发DING额度](https://oa.dingtalk.com/index.htm#/dataCenter/dingOrder?_dlp_=channel%3Dopenpf_web_devdoc_apiDING)

调用本接口，可使用企业内机器人发送DING消息，可发送应用内DING、短信DING、电话DING。

## 权限

要调用此API，需要以下权限之一。

| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| --- | --- | --- | --- |
| 企业内部应用 | 支持 | 企业机器人发送撤回DING消息 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=robot_1.0%23RobotSendDing) |
| 第三方企业应用 | 暂不支持 | 暂不支持 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/robot/ding/send HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "robotCode" : "String",
  "remindType" : Integer,
  "receiverUserIdList" : [ "String" ],
  "content" : "String",
  "callVoice" : "String"
}
```

## Header参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过调用[获取企业内部应用的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 |

## Body参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| robotCode | String | 是 | 发DING消息的机器人ID。  **说明**  创建企业内部应用机器人后，获取机器人robotCode。详情步骤请参考[机器人唯一标识](https://open.dingtalk.com/document/development/robot-overview)。 |
| remindType | Integer | 是 | DING消息类型：   * 1：应用内DING * 2：短信DING * 3：电话DING   **说明**   * 短信 DING 和电话 DING 需要单独购买权益包。本接口在没有购买短信 DING 和电话 DING的情况下，仅支持发送应用内 DING。 * 可登录[钉钉管理后台](https://oa.dingtalk.com/)，单击左侧导航栏增值服务 > 产品专区进行购买。 ![[development-robot-sends-nail-message_O1CN013xsYNP1igwml7AA04_!!6000000004443-2-tps-2878-1206.png]] |
| receiverUserIdList | Array of String | 是 | 接收人userId列表。   * 应用内DING消息，每次接收人不能超过200个。 * 短信DING和电话DING，每次接收人不能超过20个。 |
| content | String | 是 | DING消息内容。 |
| callVoice | String | 否 | 电话音色，非电话DING该字段无效，目前支持的音色枚举值：  ``` - Standard_Female_Voice - Cantonese_Female_Voice - Gentine_Female_Voice - Overbearing_Female_Voice - Lovely_Girl_Voice - Standard_Male_Voice ```  若为空为标准女性音色。 |

## 返回参数

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| openDingId | String | 发送的DING消息Id。 |
| failedList | Map | 失败的接收者列表，格式为 `{"错误原因"：[user01, user02]}`。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/robot/ding/send HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:b9c5eb0772bf3a3283023ab67c*****
Content-Type:application/json

{
  "robotCode" : "dinggtkolxz1u****eqd",
  "remindType" : 1,
  "receiverUserIdList" : [ "manager7675" ],
  "content" : "钉钉，让进步发生",
  "callVoice" : "● Standard_Female_Voice"
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
  "openDingId" : "54165xxx"
}
```

## 错误码

| HttpCode | 错误码 | 错误信息 | 说明 |
| --- | --- | --- | --- |
| 400 | send.ding.exception | send.ding.exception %s | 发送DING消息异常 |
| 400 | invalid.chatbotId | invalid.chatbotId %s | 无效的机器人id |
| 400 | miss.staffId | miss.staffId %s | 无效的接收者id |
| 400 | toomuch.msg | send too fast | 消息发送太快，每分钟每机器人发送消息<6000 |
| 400 | invalidParameter.param.invalid | 参数不合法%s | 参数不合法 |
| 400 | ding.receivercount.limit | ding receiver count limit | 钉消息接收人超出限制，应用内<200，短信\电话<20 |
| 400 | ding.serverquota.insufficient | ding server quota insufficient | 发送钉消息权益不足，需充值 |
| 500 | system.error | system.error | 系统异常 |