---
title: "获取内购商品SKU页面地址旧版SDK"
source: "https://open.dingtalk.com/document/development/obtain-the-address-of-the-product-sku-details-page"
category: "服务端API / 应用市场 / 应用内购"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-the-address-of-the-product-sku-details-page_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-the-address-of-the-product-sku-details-page_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-02-27通过此接口获取内购商品的SKU选择页面地址，用于在应用中跳转至指定商品的规格选择页。

### **使用场景**

本接口适用于服务商在钉钉生态内提供内购商品服务时，动态生成商品规格选择页面链接的业务流程。典型使用场景包括：

* **非固定价格商品**：当商品价格由调用方自定义（如按客户报价）时，需通过 `extend_param` 参数传入具体价格，跳转至对应的SKU页面。
* **固定规格商品**：对于已预设多个规格和价格的商品，可直接通过 `goods_code` 获取SKU页面，用户可在页面中选择具体规格。

该接口主要服务于**第三方企业应用**，目前企业内部应用与第三方个人应用暂不支持调用。

内购商品页面地址如下图所示，页面上展示的多个规格即为创建商品时所添加的规格。

![[development-obtain-the-address-of-the-product-sku-details-page_p492585.png]]

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 暂不支持 | 暂不支持 | 暂不支持 |
| 第三方企业应用 | 支持 | 开通应用在应用市场的内购订单的数据管理权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=dingtalk.oapi.appstore.internal.skupage.get) |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/appstore/internal/skupage/get`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | 6d1bxxxx | 调用本接口的访问凭证，通过调用获[服务商获取第三方应用授权企业的access\_token](/document/development/obtain-isvapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| goods\_code | String | 是 | FW\_GOODS\_1111 | 内购商品码。 ![[development-obtain-the-address-of-the-product-sku-details-page_p492586.png]] |
| callback\_page | String | 否 | http%3A//dingtalk.com%3Fa%3Db | 回调页面地址（需经过URL编码），微应用填写页面URL，E应用填写页面路径地址。  **重要**  http模式下，页面地址必须与应用的主域名一致，否则无法正常跳转。 |
| extend\_param | String | 否 | %7B%22outDefinedPrice%22%3A19999%7D | 调用方扩展参数。   * 若为**非固定规格**内购商品，该参数必填，且必须进行 **UrlEncode** 处理，用于指定商品价格。  参数格式为{"outDefinedPrice":199}，表示该商品价格为1.99元。 * 如果是**固定规格**内购商品，该参数可不填写。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| result | String | https://dingtalk.com | 内购商品SKU页面地址。 |
| errmsg | String | ok | 返回码描述。 |
| errcode | Number | 0 | 返回码。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/appstore/internal/skupage/get?access_token=ACCESS_TOKEN
```

**请求正文**

```json
{
        "goods_code":"FW_GOODS_1111",
        "callback_page":"http%3A//dingtalk.com%3Fa%3Db",
        "extend_param":"%7B%22outDefinedPrice%22%3A19999%7D"
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/appstore/internal/skupage/get");
OapiAppstoreInternalSkupageGetRequest req = new OapiAppstoreInternalSkupageGetRequest();
req.setGoodsCode("FW_GOODS_1111");
req.setCallbackPage("http%3A//dingtalk.com%3Fa%3Db");
req.setExtendParam("%7B%22outDefinedPrice%22%3A19999%7D");
OapiAppstoreInternalSkupageGetResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
        "result":"https://dingtalk.com",
        "errcode":"0",
        "errmsg":"ok"
}
```

## 应用链接跳转到SKU页面地址

### **移动端**

|  |  |
| --- | --- |
| **应用类型** | **打开方法** |
| H5微应用 | 调用前端JSAPI-[打开目标页面](/document/isvapp/open-the-target-page)。 |
| 小程序 | 1. 目标页面引入dingtalk-jsapi。  ```    import 'dingtalk-jsapi/entry/mobile';    import openLink from 'dingtalk-jsapi/api/biz/util/openLink';    ``` 2. 在当前页面调用openLink跳转sku页面。  ```     openLink(){        openLink({          url:"https:\/\/h5.dingtalk.com\/open-mxxxxx"        })      },    ``` |

### **PC端**

PC端应用打开侧边栏，可以使用JSAPI-[打开侧边面板](/document/isvapp/open-side-panel)。