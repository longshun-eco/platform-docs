---
title: "Agoal业务数据查询"
source: "https://open.dingtalk.com/document/development/agoal-business-biz-data-query"
category: "服务端API / Agoal"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-agoal-business-biz-data-query_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-agoal-business-biz-data-query_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-07调用本接口，通过业务编码分页查询Agoal业务数据。

## 权限

要调用此API，需要以下权限之一。

| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| --- | --- | --- | --- |
| 企业内部应用 | 支持 | Agoal指标读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=agoal_1.0%23AgoalBizDataQuery) |
| 第三方企业应用 | 支持 | Agoal指标读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=agoal_1.0%23AgoalBizDataQuery) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/agoal/bizData/query?nextToken=String&maxResults=Long&bizCode=String HTTP/1.1
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
| nextToken | String | 否 | 分页位置。 |
| maxResults | Long | 否 | 分页条数。 |
| bizCode | String | 否 | 业务编码。 |

## 返回参数

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| success | Boolean | 接口调用是否成功。 |
| result | Boolean | 查询是否成功：   * **true**：成功 * **false**：失败 |
| requestId | String | 请求ID。 |
| content | Object | 数据内容。 |
| nextToken | String | 分页起始位置。 |
| maxResults | Long | 分页条数。 |
| bizInfos | Array of Object | 数据内容Map。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/agoal/bizData/query?nextToken=100&maxResults=10&bizCode=ads_axxxxrt HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:fd1c49xxxx33f5e0
Content-Type:application/json
```

Java

```go
package com.aliyun.sample;
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

```go
package main
```

Node.js

```
'use strict';
```

C#

```
using Newtonsoft.Json;
```

**返回示例**

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "success" : true,
  "result" : true,
  "requestId" : "331cd6dxxxxf54a144a",
  "content" : {
    "nextToken" : "100",
    "maxResults" : 10,
    "bizInfos" : [ {
      "user_id" : "6603cxxxxx2c59b60f",
      "org_id" : "660390xxxx1b9d09",
      "work_no" : "1000****43",
      "show_name" : "*帅",
      "is_dimission" : "N"
    }, {
      "user_id" : "4eaa1bxxxx6a523d",
      "org_id" : "660390xxxx771b9d09",
      "work_no" : "050709454*******16",
      "show_name" : "*启",
```

## 错误码

| HttpCode | 错误码 | 错误信息 | 说明 |
| --- | --- | --- | --- |
| 400 | serviceError | service error. %s | 执行异常 |
| 401 | paramIllegal | param illagal. %s | 入参错误 |