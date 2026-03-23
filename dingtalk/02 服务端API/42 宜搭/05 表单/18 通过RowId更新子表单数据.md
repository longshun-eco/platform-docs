---
title: "通过RowId更新子表单数据新版SDK"
source: "https://open.dingtalk.com/document/development/update-the-subform-data-via-rowid"
category: "服务端API / 宜搭 / 表单"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-update-the-subform-data-via-rowid_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-update-the-subform-data-via-rowid_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-12-08通过RowId更新子表单数据。

## 权限

要调用此API，需要以下权限之一。

| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| --- | --- | --- | --- |
| 企业内部应用 | 支持 | 宜搭表单数据写权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=yida_2.0%23UpdateSubTableByRowId) |
| 第三方企业应用 | 支持 | 宜搭表单数据写权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=yida_2.0%23UpdateSubTableByRowId) |
| 第三方个人应用 | 暂不支持 | 宜搭表单数据写权限 | 暂不支持 |

## 请求方法

```
POST /v2.0/yida/forms/updateSubTableByRowId HTTP/1.1
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "updateSubTableDataJson" : "String",
  "systemToken" : "String",
  "formInstanceId" : "String",
  "userId" : "String",
  "appType" : "String",
  "useLatestFormSchemaVersion" : Boolean,
  "tableFieldId" : "String",
  "useAlias" : Boolean
}
```

## Header参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](https://open.dingtalk.com/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Body参数

| 名称 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| updateSubTableDataJson | String | 是 | 用于更新子表单实例的数据，输入为数组格式：   * **key**：组件标识，宜搭表单编辑页面，高级设置中查看。 * **value**：组件内的值。 ![[development-update-the-subform-data-via-rowid_O1CN01yTqqI51eViHNpsmb2_!!6000000003877-2-tps-2662-1014.png]] |
| systemToken | String | 是 | 宜搭应用秘钥。 ![[development-update-the-subform-data-via-rowid_O1CN01jA8xVe1ZStrN1fmGj_!!6000000003194-2-tps-2698-1144.png]] |
| formInstanceId | String | 是 | 表单实例id。 |
| userId | String | 是 | 用户的userId，可调用[获取部门用户基础信息](https://open.dingtalk.com/document/development/queries-the-simple-information-of-a-department-user)接口获取用户userId。 |
| appType | String | 是 | 宜搭应用唯一标识。 |
| useLatestFormSchemaVersion | Boolean | 否 | 是否使用最新的表单版本。  **说明**  默认为不使用 |
| tableFieldId | String | 是 | 子表ID。 |
| useAlias | Boolean | 否 | 是否使用组件别名。  **说明**  开启之后，入参`updateSubTableDataJson`中组件id支持以别名形式传入。 |
| formUuid | String | 否 | 表单ID。 ![[development-update-the-subform-data-via-rowid_O1CN01HdY3Dp1PuFLl6yIFS_!!6000000001900-2-tps-2688-1160.png]] |

## 返回参数

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| result | Boolean | 更新结果。   * **true**：更新成功 * **false**：更新失败 |

## 示例

**请求示例**

HTTP

```
POST /v2.0/yida/forms/updateSubTableByRowId HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:BExxx
Content-Type:application/json

{
  "updateSubTableDataJson" : "[{\"textField_md2x1jow\":\"更新子表通过rowId\",\"textareaField_md2x1jox\":\"更新子表通过rowId\",\"rowId\":\"xxxxxxxxxxxxxxxx\"},{\"textField_md2x1jow\":\"更新子表通过rowId\",\"textareaField_md2x1jox\":\"更新子表通过rowId\",\"rowId\":\"xxxxxxxxxxxxxxxx\"}]",
  "systemToken" : "098xxxxWK7",
  "formInstanceId" : "FINST-Jxxxx24",
  "userId" : "dixxxx2232",
  "appType" : "APPxxxx",
  "useLatestFormSchemaVersion" : false,
  "tableFieldId" : "textField_xxxxjow",
  "useAlias" : false,
  "formUuid" : "FORM-8Exxxx21A"
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
  "result" : true
}
```

## 错误码

| HttpCode | 错误码 | 错误信息 | 说明 |
| --- | --- | --- | --- |
| 500 | invalidState.role.roleNotExist | 角色不存在:%s | 角色不存在 |
| 500 | unclassifiedError | 宜搭未分类的异常信息:%s | 宜搭未分类的异常信息 |
| 500 | failure.user.userNotExist | 用户不存在:%s | 用户不存在 |
| 500 | invalidParameter.corp.corpNotExist | 企业不存在:%s | 企业不存在 |
| 500 | invalidState.authorization.invalidAuthorizationInformation | 无效的认证信息:%s | 无效的认证信息 |
| 500 | failure.operation.tooManyVisitors | 平台当前访问人数过多，请稍后重试:%s | 平台当前访问人数过多，请稍后重试 |
| 500 | invalidParameter.validation.parameterValidationFailed | 参数校验失败:%s | 参数校验失败 |
| 500 | noPermission.permission.deny | 没有权限:%s | 没有权限 |