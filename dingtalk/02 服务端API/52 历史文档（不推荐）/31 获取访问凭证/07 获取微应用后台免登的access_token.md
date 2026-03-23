---
title: "获取微应用后台免登的access_token旧版SDK"
source: "https://open.dingtalk.com/document/development/obtain-the-ssotoken-for-micro-application-background-logon-free"
category: "服务端API / 历史文档（不推荐） / 获取访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-the-ssotoken-for-micro-application-background-logon-free_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-the-ssotoken-for-micro-application-background-logon-free_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-08调用本接口获取微应用后台免登的access\_token。获取的access\_token即ssotoken只在应用管理后台免登场景中使用。

**重要**

为提升接口使用体验，针对**获取访问凭证**相关接口规范进行升级，从[旧版升级到新版](https://open.dingtalk.com/document/orgapp/differences-between-server-apis-and-new-server-apis)。本文旧版规范接口文档已于2023年8月17日迁移至历史文档（不推荐）目录，且本接口仅保持现有功能，不再新增支持其他能力。

* 如果未使用本接口，推荐使用[获取微应用后台免登的accessToken](https://open.dingtalk.com/document/orgapp/obtain-the-access_token-of-the-micro-application-background-without-log-on)新版规范接口。
* 如果已使用本接口，建议您根据自身实际情况评估是否切换至推荐接口。

**说明**

ISV开发的应用后台免登用的access\_token，需使用ISV自己的corpId和SSOsecret来换取，不是管理员所在的企业的。

## 权限

服务端API是以应用维度授权的，在调用接口前，确保对应用已经添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 支持 | 默认开通，无需申请 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.sso.gettoken) |
| 第三方企业应用 | 支持 | 默认开通，无需申请 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=dingtalk.oapi.sso.gettoken) |
| 第三方个人应用 | 暂不支持 | — | — |

## 基本信息

**请求方式**：GET

**请求地址**：`https://oapi.dingtalk.com/sso/gettoken`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| corpid | String | 是 | ding1234 | 企业的corpid。 |
| corpsecret | String | 是 | 2pyNWs4LV8Ge2Mxxxx | 可以在[钉钉开发者后台](https://open-dev.dingtalk.com/fe/old#/corpAuthInfo)的**基本信息 > 开发信息（旧版**）页面获取**微应用管理后台SSOSecret**。  如下图所示： ![[development-obtain-the-ssotoken-for-micro-application-background-logon-free_p380971.png]] |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| access\_token | String | 67477fed82e63563a320xxxx | 获取到的凭证。 |
| errmsg | String | ok | 错误信息。 |
| errcode | Number | 0 | 错误码。 |

## 示例

**请求示例（HTTP）**

```http
GET https://oapi.dingtalk.com/sso/gettoken?corpid=ding1234&corpsecret=12345
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/sso/gettoken");
OapiSsoGettokenRequest req = new OapiSsoGettokenRequest();
req.setCorpid("ding1234");
req.setCorpsecret("2pyNWs4LV8Ge2Mxxxx");
req.setHttpMethod("GET");
OapiSsoGettokenResponse rsp = client.execute(req);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
        "access_token":"67477fed82e63563a320xxxx",
        "errcode":0,
        "errmsg":"ok"
}
```

## 相关文档

* 企业内部应用，请参考[企业管理后台应用免登](/document/orgapp/exchange-code-for-the-identity-information-of-a-microapplication-administrator)
* 第三方企业应用，请参考[企业管理后台应用免登](/document/isvapp/exchange-code-for-the-identity-information-of-a-microapplication-administrator)