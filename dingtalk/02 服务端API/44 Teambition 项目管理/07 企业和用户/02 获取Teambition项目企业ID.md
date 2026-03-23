---
title: "获取Teambition项目企业ID新版SDK"
source: "https://open.dingtalk.com/document/development/obtain-the-teambition-enterprise-id"
category: "服务端API / Teambition 项目管理 / 企业和用户"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-the-teambition-enterprise-id_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-the-teambition-enterprise-id_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-09调用本接口，根据钉钉用户userId获取该用户所属钉钉企业绑定的Teambition项目企业ID。

钉钉组织在使用项目应用时，项目应用会自动同步钉钉组织内的通讯录信息，如下图所示。

![[development-obtain-the-teambition-enterprise-id_O1CN011nIZGe1rGDvlWVo0W_!!6000000005603-2-tps-2610-1338.png]]

在项目应用中会对应给每个钉钉组织生成唯一标识ID。调用本接口，可根据某个钉钉用户userId获取该员工所在钉钉组织在项目中的标识ID。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 调用钉钉项目管理相关接口的权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=project_1.0%23GetTbOrgIdByDingOrgId) |
| 第三方企业应用 | 支持 | 调用钉钉项目管理相关接口的权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=project_1.0%23GetTbOrgIdByDingOrgId) |
| 第三方个人应用 | 暂不支持 | 调用钉钉项目管理相关接口的权限 | 暂不支持 |

## 请求方法

```
GET /v1.0/project/teambition/organizations?optUserId=String HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Query参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| optUserId | String | 是 | 操作者userId。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| result | Object | 返回结果。 |
| tbOrganizationId | String | 钉钉组织在Teambition项目内的企业标识ID。 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/project/teambition/organizations?optUserId=0175xxxx HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:xxxx
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
  "result" : {
    "tbOrganizationId" : "50c32afae8cf1xxxx"
  }
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | user.not.exist | user not exist | 用户在当前企业中不存在 |
| 400 | org.not.exist | org not exist | 当前企业在Teambition中不存在 |
| 500 | server.error | system error | 系统内部服务错误 |