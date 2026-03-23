---
title: "获取 Agoal 组织目标列表新版SDK"
source: "https://open.dingtalk.com/document/development/api-agoalorgobjectivelist"
category: "服务端API / Agoal"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-agoalorgobjectivelist_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-agoalorgobjectivelist_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-12-16调用本接口获取组织目标列表。

## 权限

要调用此API，需要以下权限之一。

| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| --- | --- | --- | --- |
| 企业内部应用 | 支持 | Agoal组织目标读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=agoal_1.0%23AgoalOrgObjectiveList) |
| 第三方企业应用 | 支持 | Agoal组织目标读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=agoal_1.0%23AgoalOrgObjectiveList) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/agoal/orgObjectives/list?dingTeamId=String&periodId=String&pageNumber=Integer&pageSize=Integer HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Query参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| dingTeamId | String | 否 | 钉钉部门 id，传则只返回该部门下的组织目标，否则返回组织下的组织目标 |
| periodId | String | 否 | 周期 id，传则只返回该周期下的组织目标 |
| pageNumber | Integer | 是 | 分页页码 |
| pageSize | Integer | 否 | 分页大小 |

## 返回参数

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| requestId | String | 请求id。 |
| success | Boolean | 请求是否成功。 |
| content | OpenAgoalOrgObjectiveListDTO | 组织目标对象集合 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/agoal/orgObjectives/list?dingTeamId=853530516&periodId=662e006fe4b0f579bbcxxxxx&pageNumber=1&pageSize=10 HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:9801a354e3d03539baa83e5f275axxxx
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
  "requestId" : "E6F8BAA4-6C37-168D-858A-F2A83437755D",
  "success" : true,
  "content" : {
    "totalCount" : 100,
    "objectiveList" : [ {
      "objectiveId" : "6444f5e9a4261c6e699dxxxx",
      "title" : "测试目标",
      "status" : "formalEffective",
      "executor" : {
        "userId" : "6444f5e9a4261c6e699dxxxx",
        "dingUserId" : "211042291978xxxx",
        "name" : "测试"
      },
      "team" : {
        "teamId" : "6444f5e9a4261c6e699dxxxx",
        "deptId" : "8535683xx",
        "name" : "测试部门"
```

## 错误码

| HttpCode | 错误码 | 错误信息 | 说明 |
| --- | --- | --- | --- |
| 500 | error.systemError | 系统异常 | 系统异常 |
| 500 | error.dingTeamIdInvalid | 无效的部门 id | 无效的部门 id |