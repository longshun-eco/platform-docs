---
title: "获取个人应用内购商品SKU页面地址新版SDK"
source: "https://open.dingtalk.com/document/development/obtain-the-sku-page-address-of-goods-purchased-in-personal"
category: "服务端API / 应用市场"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-the-sku-page-address-of-goods-purchased-in-personal_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-the-sku-page-address-of-goods-purchased-in-personal_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-02-27调用本接口获取内购商品SKU页面地址。调用本接口可获取个人应用内购商品的SKU选择页面URL，用于前端跳转或分享。该接口适用于动态配置价格的内购场景，支持非固定规格商品的价格传入。

### **使用场景**

本接口适用于第三方个人应用在用户购买非固定规格内购商品时，动态生成SKU选择页面地址，并跳转至钉钉内购页面完成交易。常见于付费、订阅等需要自定义价格的业务场景。开发者可通过`extendParam`参数指定实际成交价格，实现灵活定价策略。

内购商品SKU页面如下图所示，页面中展示的多个规格即为创建商品时所添加的规格选项。

![[development-obtain-the-sku-page-address-of-goods-purchased-in-personal_个人应用内购SKU.png]]

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 暂不支持 | 暂不支持 | 暂不支持 |
| 第三方企业应用 | 暂不支持 | 暂不支持 | 暂不支持 |
| 第三方个人应用 | 支持 | 个人应用在应用市场开通购买的数据读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=personal&api=appMarket_1.0%23GetInAppSkuUrl) |

## 请求方法

```
POST /v1.0/appMarket/internal/skupage/get HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "goodsCode" : "String",
  "itemCode" : "String",
  "callbackPage" : "String",
  "extendParam" : "String"
}
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 接口调用凭证，调用[获取用户token](/document/development/obtain-user-token)接口获取。 |

## Body参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| goodsCode | String | 是 | 内购商品码。 |
| itemCode | String | 否 | 内购规格码。 |
| callbackPage | String | 否 | 回调页面（需进行UrlEncode处理），为小程序页面路径地址。 |
| extendParam | String | 否 | 调用方扩展参数：   * 如果是非固定规格内购商品，该参数必填，用于指定商品价格。 参数格式为{"outDefinedPrice":199}，表示该商品价格为1.99元。   **说明**  `extend_param`参数必须UrlEncode处理。若为固定规格内购商品，该参数可选，无需填写。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| url | String | 内购商品SKU页面地址。 |

## 示例

**请求示例**

HTTP

```
POST /v1.0/appMarket/internals/skuPages/query HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:6d1bxxxx
Content-Type:application/json

{
  "goodsCode" : "FW_GOODS_1111",
  "itemCode" : "FW_GOODS_1111_1",
  "callbackPage" : "http%3A//dingtalk.com%3Fa%3Db",
  "extendParam" : "%7B%22outDefinedPrice%22%3A19999%7D"
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
  "url" : "https://dingtalk.com 6d1bxxxx"
}
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | goodsNotExist | 内购商品不存在 | 内购商品不存在 |
| 400 | goodsItemNotExist | 商品规格不存在 | 商品规格不存在 |
| 400 | notFixedItemExtendParamError | 非固定规格扩展参数异常 | 非固定规格扩展参数异常 |
| 400 | notFixedItemNoPrice | 内购商品非固定规格未传入价格 | 内购商品非固定规格未传入价格 |
| 400 | notFixedItemInvalidPrice | 内购商品非固定规格传入价格异常 | 内购商品非固定规格传入价格异常 |