---
title: "通讯录userId排序新版SDK"
source: "https://open.dingtalk.com/document/development/address-book-userid-sorting"
category: "服务端API / 通讯录管理 / 用户管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-address-book-userid-sorting_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-address-book-userid-sorting_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-11调用本接口，根据用户姓名拼音进行userId排序。

### 接口功能介绍

调用本接口，根据用户姓名拼音进行userId排序，排序上限为100个userId。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 暂不支持 | 成员信息读权限 | 暂不支持 |
| 第三方企业应用 | 支持 | 成员信息读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=contact_1.0%23SortUser) |
| 第三方个人应用 | 暂不支持 | 成员信息读权限 | 暂不支持 |

## 请求方法

```
POST /v1.0/contact/users/sort HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "userIdList" : [ "String" ],
  "sortType" : Integer
}
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| userIdList | Array of String | 是 | 用户userId，可通过[通过免登码获取用户信息](/document/development/obtain-the-userid-of-a-user-by-using-the-log-free)获得userid参数值。 |
| sortType | Integer | 否 | 排序方式，取值为：   * **0**：根据姓名拼音升序排列 * **1**：根据姓名拼音降序排列 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| userIdList | Array of String | 用户userId。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/contact/users/sort HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:BE1xxxx
Content-Type:application/json

{
  "userIdList" : [ "45252328xxx" ],
  "sortType" : 0
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
  "userIdList" : [ "27014752071167122" ]
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 500 | listsize.too.long | userId列表超过100 | userId列表超过100 |
| 500 | system.busy | 系统繁忙 | 系统繁忙 |