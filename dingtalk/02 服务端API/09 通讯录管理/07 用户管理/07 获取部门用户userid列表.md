---
title: "获取部门用户userid列表旧版SDK"
source: "https://open.dingtalk.com/document/development/query-the-list-of-department-userids"
category: "服务端API / 通讯录管理 / 用户管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-query-the-list-of-department-userids_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-query-the-list-of-department-userids_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-10调用本接口获取指定部门的userid列表。

**说明**

本接口不受通讯录权限范围限制。

**重要**

**目前暂不支持一次性获取企业下所有员工userid值**，如果开发者希望获取企业下所有员工userid值，可以通过以下方法：

* 调用[获取部门列表](/document/development/obtain-the-department-list-v2)接口，通过逐级遍历，获取该企业下在授权范围内的所有部门ID。
* 调用本文档接口，分别获取每一个部门下的员工userid。

![[development-query-the-list-of-department-userids_p371645.png]]

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 是 | 成员信息读权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.user.listid) |
| 第三方企业应用 | 是 | 成员信息读权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=dingtalk.oapi.user.listid) |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/user/listid`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | be3Fxxxx | 调用该API的应用凭证。   * 企业内部应用，通过[获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)接口获取。 * 第三方企业应用，通过[获取第三方企业的access\_token](/document/development/obtain-isvapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| dept\_id | Number | 是 | 100 | 部门deptId，可通过调用[获取部门列表](/document/development/obtain-the-department-list-v2)获取部门deptId。  **说明**  如果是根部门，该参数传1。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| request\_id | String | 4f9kasjdhop | 请求ID。 |
| errcode | Number | 0 | 返回码。 |
| errmsg | String | ok | 返回码描述。 |
| result | ListUserByDeptResponse |  | 返回结果。 |
| userid\_list | String[] | ["zxxxx","lixxxi"] | 指定部门的userid列表。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/user/listid?access_token=ACCESS_TOKEN
```

请求正文

```json
{
 "dept_id":10
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/user/listid");
OapiUserListidRequest req = new OapiUserListidRequest();
req.setDeptId(100L);
OapiUserListidResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
    "errcode": 0,
    "errmsg":"ok",
    "result": {
        "userid_list": [
            "usxxx",
            "manager4xxx",
            "10203029011xxxx",
            "usexxx"
        ]
    },
    "request_id": "3naksldjh0dk"
}
```

## 错误码

|  |  |  |
| --- | --- | --- |
| 错误码（errcode） | 错误码描述（errmsg） | 解决方案 |
| 60003 | 未找到部门 | 请确认dept\_id是否正确 |
| 400002 | 无效的参数 | 请确认参数是否合法 |
| -1 | 系统繁忙 | 请稍后重试 |