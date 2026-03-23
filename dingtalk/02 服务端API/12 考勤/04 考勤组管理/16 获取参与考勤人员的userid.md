---
title: "获取参与考勤人员的userid旧版SDK"
source: "https://open.dingtalk.com/document/development/query-attendance-group-personnel-information-in-batches"
category: "服务端API / 考勤 / 考勤组管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-query-attendance-group-personnel-information-in-batches_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-query-attendance-group-personnel-information-in-batches_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-10调用本接口，分页获取某个考勤组下的所有员工的userId。

**说明**

如果参与考勤人员设置了部门，接口返回部门下的员工的userId，不返回部门ID。

例如，参与考勤人员设置了**测试部门**、员工**张三**，测试部门下有一个员工**李四**。调用本接口可以获取到如下信息：

* 测试部门（包括子部门）下的员工的userId，即李四的userId
* 员工张三的员工userId

![[development-query-attendance-group-personnel-information-in-batches_p960306.png]]

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 是 | 考勤组查询权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.attendance.group.memberusers.list) |
| 第三方企业应用 | 是 | 考勤组查询权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=dingtalk.oapi.attendance.group.memberusers.list) |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/attendance/group/memberusers/list`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | 6d1bxxxx | 调用该API的应用凭证。   * 企业内部应用，通过[获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)接口获取。 * 第三方企业应用，通过[获取第三方企业的access\_token](/document/development/obtain-isvapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| cursor | Number | 否 | 0 | 游标值，表示从第几个开始，不传默认从第一个开始。 |
| op\_user\_id | String | 是 | user123 | 操作人userId。 |
| group\_id | Number | 是 | 98562 | 考勤组ID。  **说明**  如果你使用的是旧考勤组标识即group\_key，可以调用[groupKey转换为groupId](/document/development/convert-groupkey-to-groupid)接口将group\_key转换为group\_id。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| request\_id | String | 3pgsafymemlr | 请求ID。 |
| errcode | Number | 0 | 返回码。 |
| success | Boolean | true | 是否成功标记。   * **true**：成功 * **false**：失败 |
| result | PageResult |  | 人员列表。 |
| has\_more | Boolean | false | 是否还有更多数据。   * **true**：有 * **false**：没有 |
| cursor | Number | 1387570559 | 分页获取下一次请求的起始位置。 |
| result | String[] | ["user123","user456"] | 考勤组人员userId列表。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/attendance/group/memberusers/list?access_token=ACCESS_TOKEN
```

请求正文

```json
{
        "op_user_id":"user123",
        "group_id":98562,
        "cursor":0
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/attendance/group/memberusers/list");
OapiAttendanceGroupMemberusersListRequest req = new OapiAttendanceGroupMemberusersListRequest();
req.setCursor(0L);
req.setOpUserId("user123");
req.setGroupId(98562L);
OapiAttendanceGroupMemberusersListResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
    "errcode": 0,
    "result": {
        "cursor": 1387570559,
        "has_more": false,
        "result": [
            "user123",
            "user456"
        ]
    },
    "success": true,
    "request_id": "146drwo74wiss"
}
```