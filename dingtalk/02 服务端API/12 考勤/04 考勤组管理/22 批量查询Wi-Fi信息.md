---
title: "批量查询Wi-Fi信息旧版SDK"
source: "https://open.dingtalk.com/document/development/batch-query-wifi-under-attendance-group"
category: "服务端API / 考勤 / 考勤组管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-batch-query-wifi-under-attendance-group_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-batch-query-wifi-under-attendance-group_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-10调用本接口，批量查询指定考勤组下的Wi-Fi列表信息。

调用本接口，可查询考勤组下的Wi-Fi信息列表。接口功能与下图中操作实现效果一致。

![[development-batch-query-wifi-under-attendance-group_p960324.png]]

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 是 | 考勤组查询权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.attendance.group.wifis.query) |
| 第三方企业应用 | 否 | — | — |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/attendance/group/wifis/query`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | 4c9ebd2b1534xxxx | 调用该接口的应用凭证，通过[获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| cursor | String | 否 | 0151E022xxxx | 上一批次最后一个Id，默认为空。 |
| size | Number | 是 | 50 | 分页大小。 |
| op\_userid | String | 否 | user01 | 操作人userId。 |
| group\_key | String | 是 | 015xxxx | 考勤组ID。  **说明**  如果你使用的考勤组标识是group\_id，可以调用[groupId转换为groupKey](/document/development/groupid-to-groupkey)接口将group\_id转换为group\_key。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| result | DingOpenResult |  | 返回结果。 |
| result | Result |  | 查询Wi-Fi列表结果。 |
| wifi\_list | Wifi[] |  | Wi-Fi列表。 |
| mac\_addr | String | 54:8D:xx:xx:xx:73 | mac地址。 |
| ssid | String | alibaba-inc | Wi-Fi名称。 |
| wifi\_key | String | E4CB0xxxx | Wi-Fi的key。 |
| has\_more | Boolean | true | 是否还有更多。   * **true**：有 * **false**：没有 |
| errcode | Number | 0 | 返回码。 |
| errmsg | String | ok | 返回码描述。 |
| success | Boolean | true | 是否成功。   * **true**：成功 * **false**：失败 |
| request\_id | String | 155qyie8nxoqu | 请求ID。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/attendance/group/wifis/query?access_token=ACCESS_TOKEN
```

请求正文

```json
{
        "cursor":"0151E022xxxx",
        "size":50,
        "op_userid":"user01",
        "group_key":"015xxxx"
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/attendance/group/wifis/query");
OapiAttendanceGroupWifisQueryRequest req = new OapiAttendanceGroupWifisQueryRequest();
req.setCursor("0151E022xxxx");
req.setSize(50L);
req.setOpUserid("user01");
req.setGroupKey("015xxxx");
OapiAttendanceGroupWifisQueryResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
    "result": {
        "errcode": 0,
        "errmsg":"ok",
        "result": {
            "has_more": false,
            "wifi_list": [
                {
                    "mac_addr": "54:8D:xx:xx:xx:73",
                    "ssid": "alibaba-inc",
                    "wifi_key": "E4CB0xxxx"
                }
            ]
        },
        "success": true
    },
    "request_id": "155qyie8nxoqu"
}
```