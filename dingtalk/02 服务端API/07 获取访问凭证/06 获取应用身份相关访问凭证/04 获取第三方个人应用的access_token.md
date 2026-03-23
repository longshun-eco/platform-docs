---
title: "获取第三方个人应用的access_token旧版SDK"
source: "https://open.dingtalk.com/document/development/obtain-personal-application"
category: "服务端API / 获取访问凭证 / 获取应用身份相关访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-personal-application_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-personal-application_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22调用本接口可获取第三方个人应用的全局唯一凭证 `access_token`，用于后续调用钉钉开放平台提供的用户身份识别、数据获取等开放能力，

## 基本信息

**请求方式**：GET

**请求地址**：`https://oapi.dingtalk.com/sns/gettoken`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| appid | String | 是 | dingeqqpkv3xxxx | 创建的第三方个人应用的标识。  详情请参考[创建和配置应用](/document/dingstart/create-and-configure-an-application)。 |
| appsecret | String | 是 | GT-lsu-taDAsTsxxxx | 创建的第三方个人应用的密钥。  appid和appsecret可在[钉钉开发者后台](https://open-dev.dingtalk.com/)的应用详情页面获取。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| access\_token | String | fw8ef8we8f76e6f7s8dxxxx | 生成的access\_token。 |
| errmsg | String | ok | 返回码描述。 |
| errcode | Number | 0 | 返回码。 |

## 示例

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/sns/gettoken");
OapiSnsGettokenRequest req = new OapiSnsGettokenRequest();
req.setAppid("ding1234");
req.setAppsecret("1234");
req.setHttpMethod("GET");
OapiSnsGettokenResponse rsp = client.execute(req);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
    "errcode": 0,
    "access_token": "fw8ef8we8f76e6f7s8dxxxx",
    "errmsg": "ok"
}
```