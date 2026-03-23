---
title: "批量新增Wi-Fi信息旧版SDK"
source: "https://open.dingtalk.com/document/development/batch-add-wifi-under-attendance-group"
category: "服务端API / 考勤 / 考勤组管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-batch-add-wifi-under-attendance-group_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-batch-add-wifi-under-attendance-group_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-10调用本接口，为指定考勤组批量新增Wi-Fi信息。

调用本接口，为考勤组添加办公Wi-Fi。接口调用效果与下图操作实现效果一致。

![[development-batch-add-wifi-under-attendance-group_p960317.png]]

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 是 | 考勤组管理权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.attendance.group.wifis.add) |
| 第三方企业应用 | 否 | — | — |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/attendance/group/wifis/add`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | 1eb68xxx | 调用该接口的应用凭证，通过[获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| op\_userid | String | 否 | user01 | 操作人的userId。 |
| group\_key | String | 是 | 0151E0xxx | 考勤组ID。  **说明**  如果你使用的考勤组标识是group\_id，可以调用[groupId转换为groupKey](/document/development/groupid-to-groupkey)接口将group\_id转换为group\_key。 |
| wifi\_list | Wifi[] | 是 |  | Wi-Fi列表，每次调用最多新增100个Wi-Fi信息。 |
| foreign\_id | String | 是 | alibaba-inc | 业务方wifiId。 |
| mac\_addr | String | 是 | 11:11:11:11:11:11 | MAC地址。 |
| ssid | String | 是 | alibaba-inc1 | 名称。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| result | DingOpenResult |  | 返回的信息。 |
| result | Result |  | 添加Wi-Fi结果。 |
| error\_info\_list | ErrorInfo[] |  | 添加失败的Wi-Fi列表。 |
| failure\_list | Wifi[] |  | 失败列表。 |
| foreign\_id | String | alibaba-guest | 业务方wifiId。 |
| mac\_addr | String | 02:10:18:11:11:11 | MAC地址。 |
| ssid | String | alibaba-guest1 | MAC名称。 |
| wifi\_key | String | 01xxxxE876 | 添加Wi-Fi失败的key。 |
| msg | String | business fault | 错误描述。 |
| code | String | 1000 | 错误码。 |
| success\_list | Wifi[] |  | 添加成功的Wi-Fi列表。 |
| foreign\_id | String | alibaba-inc | 业务方wifiId。 |
| mac\_addr | String | 11:11:11:11:11:11 | MAC地址。 |
| ssid | String | alibaba-inc1 | MAC名称。 |
| wifi\_key | String | 01xxxxE876 | 添加Wi-Fi成功的key。 |
| errcode | Number | 0 | 返回码。 |
| errmsg | String | ok | 返回码描述。 |
| success | Boolean | true | 是否成功。   * **true**：成功 * **false**：失败 |
| request\_id | String | wicoxqraqt0g | 请求ID。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/attendance/group/wifis/add?access_token=ACCESS_TOKEN
```

请求正文

```json
{
    "wifi_list": [
        {
            "foreign_id": "alibaba-guest",
            "mac_addr": "02:10:18:11:11:11",
            "ssid": "alibaba-guest1"
        },
         {
            "foreign_id": "alibaba-inc",
            "mac_addr": "11:11:11:11:11:11",
            "ssid": "alibaba-guest1"
        }
    ],
    "op_userid": "user01",
    "group_key": "0151E0xxx"
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/attendance/group/wifis/add");
OapiAttendanceGroupWifisAddRequest req = new OapiAttendanceGroupWifisAddRequest();
List wifis = new ArrayList<>();
// 第一条WiFi信息
Wifi wifi1 = new Wifi();
wifis.add(wifi1);
wifi1.setForeignId("alibaba-inc");
wifi1.setMacAddr("11:11:11:11:11:11");
wifi1.setSsid("alibaba-inc1");
// 第二条WiFi信息 （ps： 错误的信息）
Wifi wifi2 = new Wifi();
wifis.add(wifi2);
wifi2.setForeignId("alibaba-guest");
wifi2.setMacAddr("02:10:18:11:11:11");
wifi2.setSsid("alibaba-guest1");

req.setOpUserid("user01");
req.setGroupKey("0151E0xxx");
req.setWifiList(wifis);
OapiAttendanceGroupWifisAddResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```
{
    "result": {
        "errcode": 0,
        "errmsg":"ok",
        "result": {
            "error_info_list": [
                {
                    "code": "1000",
                    "failure_list": [
                        {
                            "foreign_id": "alibaba-guest",
                            "mac_addr": "02:10:18:11:11:11",
                            "ssid": "alibaba-guest1"
                        }
                    ],
                    "msg": "business fault"
                }
            ],
            "success_list": [
                {
                    "foreign_id": "alibaba-inc",
```