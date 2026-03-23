---
title: "根据groupKey查询考勤组信息旧版SDK"
source: "https://open.dingtalk.com/document/development/queries-attendance-group-information-by-id"
category: "服务端API / 考勤 / 考勤组管理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-queries-attendance-group-information-by-id_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-queries-attendance-group-information-by-id_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-10本接口根据考勤组groupKey查询考勤组信息。

例如，考勤组部分信息如下图所示。调用本接口，可获取打卡范围、是否允许外勤打卡、外勤打卡是否需要审批等信息。

![[development-queries-attendance-group-information-by-id_p960273.png]]

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 是 | 考勤组查询权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.attendance.group.get) |
| 第三方企业应用 | 否 | — | — |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/attendance/group/get`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | 4c9ebd2b1534xxxx | 调用该接口的应用凭证，通过[获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| op\_userid | String | 否 | user123 | 操作人userId。 |
| group\_key | String | 是 | 02B1Exxxx | 考勤组groupKey。  **说明**  如果你使用的考勤组标识是group\_id，可以调用[groupId转换为groupKey](/document/development/groupid-to-groupkey)接口将group\_id转换为group\_key。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| result | Object |  | 考勤组信息结果。 |
| name | String | 测试考勤组1 | 考勤组名称。 |
| ext | String |  | 扩展字段，JSON格式。 |
| location\_offset | Number | 100 | 打卡范围，单位为米。  **说明**  该字段已废弃，请以[批量查询地点](/document/development/batch-query-position-under-attendance-group)接口返回的offset为准。 |
| group\_key | String | 0151E0223B1EDDDF00DD6B7F72A1A917 | 考勤组groupKey。 |
| enable\_face\_check | Boolean | false | 是否开启笑脸打卡。   * **true**：开启 * **false**（默认）：关闭 |
| enable\_face\_beauty | Boolean | false | 是否开启美颜。   * **true**：开启 * **false**（默认）：关闭 |
| enable\_camera\_check | Boolean | false | 是否开启拍照打卡。   * **true**：开启 * **false**（默认）：关闭 |
| enable\_outside\_check | Boolean | false | 是否允许外勤打卡。   * **true**：允许 * **false**（默认）：不允许 |
| enable\_outside\_apply | Boolean | false | 外勤打卡是否需要审批。   * **true**：需要 * **false**（默认）：不需要 |
| outside\_check\_approve\_mode | Number | 0 | 外勤打卡审批模式。   * **-1**（默认）：关闭 * **0**：先审批，再打卡 * **1**：先打卡，再审批 |
| enable\_outside\_remark | Boolean | false | 外勤打卡是否需要填写备注。   * **true**：需要 * **false**（默认）：不需要 |
| enable\_outside\_camera\_check | Boolean | false | 外勤打卡是否需要拍照备注。   * **true**：需要 * **false**（默认）：不需要 |
| forbid\_hide\_outside\_address | Boolean | true | 是否禁止员工隐藏详细地址。   * **true**（默认）：禁止 * **false**：不禁止 |
| enable\_outside\_update\_normal\_check | Boolean | false | 是否允许外勤卡更新内勤卡。   * **true**：允许 * **false**（默认）：不允许 |
| enable\_trim\_distance | Boolean | false | 是否允许地点微调距离。   * **true**：允许 * **false**（默认）：不允许 |
| trim\_distance | Number | 50 | 地点微调范围，单位为米。 |
| errmsg | String | ok | 返回的错误信息描述。 |
| success | Boolean | true | 是否成功。   * **true**：成功 * **false**：失败 |
| errcode | Number | 0 | 错误码。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/attendance/group/get?access_token=ACCESS_TOKEN
```

请求正文

```json
{
        "op_userid":"123456",
        "group_key":"0151E0223B1EDDDF00DD6B7F72A1A917"
}
```

**请求示例（JAVA SDK）**

```java
public class Main {
    public static void main(String[] args) {
        try {
            DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/attendance/group/get");
            OapiAttendanceGroupGetRequest req = new OapiAttendanceGroupGetRequest();
            OapiAttendanceGroupGetResponse rsp = client.execute(req, "");
            System.out.println(rsp.getBody());
        } catch (ApiException e) {
            e.printStackTrace();
        }
    }
}
```

**返回示例**

```
{
        "result":{
                "ext":"",
                "enable_camera_check":false,
                "enable_face_beauty":false,
                "outside_check_approve_mode":0,
                "forbid_hide_outside_address":true,
                "enable_face_check":false,
                "enable_outside_apply":false,
                "enable_outside_camera_check":false,
                "enable_outside_update_normal_check":false,
                "trim_distance":50,
                "enable_outside_check":false,
                "location_offset":100,
                "enable_outside_remark":false,
                "name":"测试考勤组1",
                "group_key":"0151E0223B1EDDDF00DD6B7F72A1A917",
                "enable_trim_distance":false
        },
        "errcode":0,
        "success":true,
```