---
title: "批量移除Wi-Fi信息旧版SDK"
source: "https://open.dingtalk.com/document/development/batch-remove-wifi-under-attendance-group"
category: "服务端API / 考勤 / 考勤组管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-batch-remove-wifi-under-attendance-group_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-batch-remove-wifi-under-attendance-group_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-10调用本接口，批量移除指定考勤组的Wi-Fi信息。

调用本接口，可删除指定考勤组的Wi-Fi。接口功能与下图操作实现效果一致。

![[development-batch-remove-wifi-under-attendance-group_p960324.png]]

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 是 | 考勤组管理权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.attendance.group.wifis.remove) |
| 第三方企业应用 | 否 | — | — |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/attendance/group/wifis/remove`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | 6d1bxxxx | 调用该接口的应用凭证，通过[获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| op\_userid | String | 否 | user01 | 操作人userId。 |
| group\_key | String | 是 | CEDDFxxxx | 考勤组ID。  **说明**  如果你使用的考勤组标识是group\_id，可以调用[groupId转换为groupKey](/document/development/groupid-to-groupkey)接口将group\_id转换为group\_key。 |
| wifi\_key\_list | String | 是 | 0151Exxxx | Wi-Fi的key，可通过[批量查询Wi-Fi信息](/document/development/batch-query-wifi-under-attendance-group)接口获取，每次调用最多支持移除100个Wi-Fi信息。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| result | Result |  | 删除成功的wifiId列表。 |
| error\_info\_list | ErrorInfo[] |  | 失败列表。 |
| failure\_list | String[] | 0151EEDDDF0xxxx | 错误列表。 |
| msg | String | business fault | 错误描述。 |
| code | String | 1000 | 错误码。 |
| success\_list | String[] | 0151EEDDDF0xxxx | 成功列表。 |
| errcode | Number | 0 | 返回码。 |
| errmsg | String | ok | 返回码描述。 |
| success | Boolean | true | 是否成功。   * **true**：成功 * **false**：失败 |
| request\_id | String | 7o76z7s5cett | 请求ID。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/attendance/group/wifis/remove?access_token=ACCESS_TOKEN
```

请求正文

```json
{
        "wifi_key_list":"0151Exxxx",
        "op_userid":"user01",
        "group_key":"CEDDFxxxx"
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/attendance/group/wifis/remove");
OapiAttendanceGroupWifisRemoveRequest req = new OapiAttendanceGroupWifisRemoveRequest();
req.setOpUserid("user01");
req.setGroupKey("CEDDFxxxx");
req.setWifiKeyList("0151Exxxx");
OapiAttendanceGroupWifisRemoveResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
    "errcode": 0,
    "errmsg":"ok",
    "result": {
        "success_list": [
            "0151Exxxx",
 ]
    },
    "success": true,
    "request_id": "7o76z7s5cett"
}
```