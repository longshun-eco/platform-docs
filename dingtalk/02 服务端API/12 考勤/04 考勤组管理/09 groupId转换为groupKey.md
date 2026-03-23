---
title: "groupId转换为groupKey旧版SDK"
source: "https://open.dingtalk.com/document/development/groupid-to-groupkey"
category: "服务端API / 考勤 / 考勤组管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-groupid-to-groupkey_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-groupid-to-groupkey_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-10调用本接口，将考勤组的groupId转换为groupKey。

groupKey为考群组新版字段的标识，部分考勤组需要使用groupKey为参数，如果当前仅有考勤组groupId字段，可调用本接口获取groupKey。

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 是 | 考勤组查询权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.attendance.groups.idtokey) |
| 第三方企业应用 | 是 | 考勤组查询权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=dingtalk.oapi.attendance.groups.idtokey) |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/attendance/groups/idtokey`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | 6d1bxxxx | 调用该API的应用凭证。   * 企业内部应用，通过[获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)接口获取。 * 第三方企业应用，通过[获取第三方企业的access\_token](/document/development/obtain-isvapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| op\_user\_id | String | 否 | user01 | 操作人的userId。 |
| group\_id | Number | 是 | 1586536 | 考勤组ID，可调用[批量获取考勤组详情](/document/development/batch-obtain-attendance-group-details)接口获取group\_id参数值。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| result | String | 0151E0223B1xxxx | 考勤组ID。 |
| errcode | Number | 0 | 返回码。 |
| errmsg | String | ok | 返回码描述。 |
| request\_id | String | 3yt2gu3zz0qi | 请求ID。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/attendance/groups/idtokey?access_token=ACCESS_TOKEN
```

请求正文

```json
{
 "op_user_id":"user01",
 "group_id":1586536
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/attendance/groups/idtokey");
OapiAttendanceGroupsIdtokeyRequest req = new OapiAttendanceGroupsIdtokeyRequest();
req.setOpUserId("user01");
req.setGroupId(1586536L);
OapiAttendanceGroupsIdtokeyResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
 "errcode":0,
 "result":0151E0223B1xxxx,
 "errmsg":"ok",
 "request_id":"3yt2gu3zz0qi"
}
```