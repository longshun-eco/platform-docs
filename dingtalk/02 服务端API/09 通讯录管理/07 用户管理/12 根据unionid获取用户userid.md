---
title: "根据unionid获取用户userid旧版SDK"
source: "https://open.dingtalk.com/document/development/query-a-user-by-the-union-id"
category: "服务端API / 通讯录管理 / 用户管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-query-a-user-by-the-union-id_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-query-a-user-by-the-union-id_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-10调用本接口根据unionid获取用户的userid。

**重要**

unionid是员工在当前开发者企业账号范围内的唯一标识，由系统生成：

* 同一个企业员工，在不同的开发者企业账号下，unionid是不相同的。
* 在同一个开发者企业账号下，unionid是唯一且不变的，例如同一个服务商开发的多个应用，或者是扫码登录等场景的多个App账号。

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 是 | 成员信息读权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.user.getbyunionid) |
| 第三方企业应用 | 是 | 成员信息读权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=dingtalk.oapi.user.getbyunionid) |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/user/getbyunionid`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | be3Fxxxx | 调用该接口的应用凭证。  **说明**  如果是通过**免登方式**获取的unionid，则不能使用免登获取的 token 调用该接口，需要使用下方的接口重新获取。   * 企业内部应用，通过[获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)接口获取。 * 第三方企业应用，通过[获取第三方企业的access\_token](/document/development/obtain-isvapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| unionid | String | 是 | z21HjQliSzpw0Yxxxx | 员工在当前开发者企业账号范围内的唯一标识，系统生成，不会改变。可通过调用[通过免登码获取用户信息](/document/development/obtain-the-userid-of-a-user-by-using-the-log-free)获取unionid。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| request\_id | String | zcqi5450rpit | 请求ID。 |
| errcode | Number | 0 | 返回码。 |
| errmsg | String | ok | 返回码描述。 |
| result | UserGetByUnionIdResponse |  | 返回结果。 |
| contact\_type | Number | 0 | 联系类型：   * **0**：企业内部员工 * **1**：企业外部联系人 |
| userid | String | zhangsan | 用户的userid。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/user/getbyunionid?access_token=ACCESS_TOKEN
```

请求正文

```json
{
 "unionid":"z21HjQliSzxxxx"
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/user/getbyunionid");
OapiUserGetbyunionidRequest req = new OapiUserGetbyunionidRequest();
req.setUnionid("z21HjQliSzpw0Yxxxxxx");
OapiUserGetbyunionidResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
  "errcode":"0",
  "errmsg":"ok",
  "result":{
   "contact_type":"0",
   "userid":"zhangsan"
  },
  "request_id": "zcqi5450rpit"
}
```

## 错误码

|  |  |  |
| --- | --- | --- |
| 错误码（errcode） | 错误码描述（errmsg） | 解决方案 |
| 60121 | 未找到对应员工 | 请检查unionId是否正确 |
| 400002 | 无效的参数 | 请检查unionId是否正确 |
| -1 | 系统繁忙 | 请稍后再试 |