---
title: "删除CRM自定义对象数据新版SDK"
source: "https://open.dingtalk.com/document/development/delete-crm-custom-object-data"
category: "服务端API / 客户管理（官方CRM） / 自定义对象"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-delete-crm-custom-object-data_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-delete-crm-custom-object-data_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-09调用本接口，删除CRM自定义对象数据。

调用本接口，删除指定的自定义对象数据。接口调用效果与下图操作实现效果一致。

![[development-delete-crm-custom-object-data_O1CN01vCzqTg1IH8BCTtn4o_!!6000000000867-2-tps-2464-936.png]]

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 维护CRM主数据的接口写入权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=crm_1.0%23DeleteCrmCustomObjectData) |
| 第三方企业应用 | 暂不支持 | 维护CRM主数据的接口写入权限 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 维护CRM主数据的接口写入权限 | 暂不支持 |

## 请求方法

```sql
DELETE /v1.0/crm/customObjectData/{instanceId}?formCode=String HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 |

## Path参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| instanceId | String | 是 | CRM自定义对象数据ID，可通过[根据指定条件查询自定义对象数据](/document/development/api-getobjectdata)接口获取instance\_id参数值。 |

## Query参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| formCode | String | 是 | 自定义对象表单code。  **说明**  在客户管理应用的**客户管理管理后台**页面，进入表单编辑页面，在最下方可查看表单code。 ![[development-delete-crm-custom-object-data_O1CN011JZDUt1pXy3hosPmE_!!6000000005371-2-tps-2486-1414.png]] |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| instanceId | String | 删除成功的CRM自定义对象数据ID。 |

## 示例

**请求示例**

HTTP

```sql
DELETE /v1.0/crm/customObjectDatas/instances/INST_XX?formCode=PROC-EFxxxx HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:c364097xxx
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
  "instanceId" : "INST_XX"
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | request.too.frequent | request too frequent | 请求过于频繁 |
| 400 | systemError.appNotExists | %s | 应用不存在 |
| 400 | systemError.notPermittedAccess | %s | 无权限操作 |
| 400 | formCode.notExists | formCode not exists | formCode不存在 |
| 400 | daily.call.limit | daily call limit | 单日调用数量已达上限，请择日再次调用 |
| 500 | systemError | system error %s | 系统错误 |