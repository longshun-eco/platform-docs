---
title: "获取Agoal指定规则周期下负责人的目标列表新版SDK"
source: "https://open.dingtalk.com/document/development/api-agoaluserobjectivelist"
category: "服务端API / Agoal"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-agoaluserobjectivelist_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-agoaluserobjectivelist_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-10调用本接口获取指定的规则周期下负责人的目标列表，目标返回值包括目标id、标题、负责人、归属团队、周期、进度、状态、关键结果、权重和所属目标规则，数组列表形式返回。

## 权限

要调用此API，需要以下权限之一。

| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| --- | --- | --- | --- |
| 企业内部应用 | 支持 | Agoal目标读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=agoal_1.0%23AgoalUserObjectiveList) |
| 第三方企业应用 | 支持 | Agoal目标读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=agoal_1.0%23AgoalUserObjectiveList) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/agoal/users/objectiveLists/query HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "objectiveRuleId" : "String",
  "periodIds" : [ "String" ],
  "dingUserId" : "String"
}
```

## Header参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Body参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| objectiveRuleId | String | 是 | 目标规则id。 |
| periodIds | Array of String | 是 | 周期id。 |
| dingUserId | String | 是 | 目标负责人dingUserId。 |

## 返回参数

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| requestId | String | 请求ID。 |
| success | Boolean | 请求是否成功。 |
| content | Array | 返回结果，目标对象数组。 |
| OpenAgoalObjectiveDTO | OpenAgoalObjectiveDTO | 目标对象。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/agoal/users/objectiveLists/query HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:9801a354e3d03539baa83e5f275axxxx
Content-Type:application/json

{
  "objectiveRuleId" : "6444f5e9a4261c6e699dxxxx",
  "periodIds" : [ "6444f5e9a4261c6e699dxxxx" ],
  "dingUserId" : "211042291978xxxx"
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
  "content" : [ {
    "objectiveId" : "6444f5e9a4261c6e699dxxxx",
    "title" : "测试目标",
    "executor" : {
      "userId" : "6444f5e9a4261c6e699dxxxx",
      "dingUserId" : "211042291978xxxx",
      "name" : "测试"
    },
    "teams" : [ {
      "teamId" : "6444f5e9a4261c6e699dxxxx",
      "deptId" : "8535683xx",
      "name" : "测试部门"
    } ],
    "period" : {
      "periodId" : "6444f5e9a4261c6e699dxxxx",
```

## 错误码

| HttpCode | 错误码 | 错误信息 | 说明 |
| --- | --- | --- | --- |
| 500 | error.systemError | 系统异常 | 系统异常 |
| 500 | error.noPermission | 无权限 | 无权限 |