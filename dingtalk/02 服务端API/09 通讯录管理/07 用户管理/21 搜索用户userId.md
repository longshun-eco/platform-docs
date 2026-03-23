---
title: "搜索用户userId新版SDK"
source: "https://open.dingtalk.com/document/development/address-book-search-user-id"
category: "服务端API / 通讯录管理 / 用户管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-address-book-search-user-id_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-address-book-search-user-id_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-11调用本接口，搜索用户userId。

### 接口功能介绍

调用本接口根据用户名称搜索用户userId，具体信息如下图。

![[development-address-book-search-user-id_O1CN01RQPule26UAEAabdGv_!!6000000007664-2-tps-285-178.png]]

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 搜索企业通讯录的权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=contact_1.0%23SearchUser) |
| 第三方企业应用 | 支持 | 搜索企业通讯录的权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=contact_1.0%23SearchUser) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
POST /v1.0/contact/users/search HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "queryWord" : "String",
  "offset" : Integer,
  "size" : Integer,
  "fullMatchField" : Integer
}
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| queryWord | String | 是 | 用户名称、名称拼音或英文名称。 |
| offset | Integer | 是 | 分页页码。 |
| size | Integer | 是 | 分页大小。 |
| fullMatchField | Integer | 否 | 是否精确匹配。   * **1**：精确匹配用户名称。   **说明**  该参数不传，默认模糊匹配用户名称。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| hasMore | Boolean | 是否还有更多数据。   * true：是 * false：否 |
| totalCount | Long | 总记录数。 |
| list | Array of String | 用户userId。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/contact/users/search HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:BExxx
Content-Type:application/json

{
  "queryWord" : "小红",
  "offset" : 0,
  "size" : 10,
  "fullMatchField" : 1
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
  "hasMore" : false,
  "totalCount" : 2,
  "list" : [ "220141953" ]
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | parameter.error | 参数错误 | 参数错误 |
| 500 | system.busy | 系统错误 | 系统错误 |