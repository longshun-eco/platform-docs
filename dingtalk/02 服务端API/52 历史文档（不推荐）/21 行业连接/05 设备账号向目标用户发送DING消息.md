---
title: "设备账号向目标用户发送DING消息新版SDK"
source: "https://open.dingtalk.com/document/development/device-publishing"
category: "服务端API / 历史文档（不推荐） / 行业连接"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-device-publishing_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-device-publishing_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-08调用本接口使用设备对应的钉钉账号，向指定人员发送DING消息

![[development-device-publishing_O1CN01zmEBjG259isht7208_!!6000000007484-2-tps-600-315.png]]

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 制造业设备DING消息发送权限 | 暂不支持 |
| 第三方企业应用 | 支持 | 制造业设备DING消息发送权限 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 制造业设备DING消息发送权限 | 暂不支持 |

## 请求方法

```
POST /v1.0/devicemng/ding HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "paramsJson" : "String",
  "deviceKey" : "String",
  "receiverUserIdList" : [ "String" ]
}
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用服务端API的应用凭证。   * 企业内部应用可通过[获取企业内部应用的access\_token](/document/orgapp/obtain-orgapp-token)接口获取 * 第三方企业应用可通过[获取第三方应用授权企业的access\_token](/document/isvapp/obtains-the-enterprise-authorized-credential)接口获取 |

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| paramsJson | String | 否 | 消息体动态参数，JSON格式为DING消息模板中的变量赋值，取值如下：   * **msgContent**：消息体内容 * **detailUrl**：消息详情链接 * **orgName**：组织名称 |
| deviceKey | String | 是 | 设备标识，生产设备的唯一标识，将据此生成钉钉账号。 |
| receiverUserIdList | Array of String | 是 | 接收消息的人员userid列表。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| result | String | 发送消息成功后的回执ID。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/devicemng/ding HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:3d60a2xxx
Content-Type:application/json

{
  "paramsJson" : "{   \"msgContent\": \"test msg!\",   \"detailUrl\": \"https://open.dingtalk.com/\",   \"orgName\": \"钉钉行业化\" }",
  "deviceKey" : "xxxx",
  "receiverUserIdList" : [ "manager123" ]
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
  "result" : "MSxxx"
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | deviceNotExist | 找不到设备 | 找不到设备 |
| 400 | deviceKeyDuplicate | 设备key重复 | 设备key重复 |
| 400 | sendDingFail | 机器人发送ding消息失败 | 机器人发送ding消息失败 |
| 500 | systemError | 系统错误 | 系统错误 |