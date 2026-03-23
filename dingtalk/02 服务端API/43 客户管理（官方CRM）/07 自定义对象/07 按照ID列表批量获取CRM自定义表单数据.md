---
title: "按照ID列表批量获取CRM自定义表单数据旧版SDK"
source: "https://open.dingtalk.com/document/development/retrieves-custom-crm-forms-from-the-id-list"
category: "服务端API / 客户管理（官方CRM） / 自定义对象"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-retrieves-custom-crm-forms-from-the-id-list_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-retrieves-custom-crm-forms-from-the-id-list_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23调用本接口，根据实例ID列表批量获取CRM自定义对象数据，最多可一次获取200条数据。

调用本接口，可按照ID列表批量获取CRM自定义表单数据，包括记录创建人的昵称、审批结果、审批状态等。

![[development-retrieves-custom-crm-forms-from-the-id-list_p373862.png]]

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 是 | 获取CRM自定义对象数据的接口访问权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.crm.objectdata.list) |
| 第三方企业应用 | 否 | — | — |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/crm/objectdata/list`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | dc73axxxx | 调用该接口的应用凭证，通过[获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| current\_operator\_userid | String | 否 | user01 | 操作人用户userId。 |
| data\_id\_list | String | 是 | INST\_XX1,INST\_XX2 | 数据ID列表，多个用英文逗号隔开，可通过[根据指定条件查询自定义对象数据](/document/development/api-getobjectdata)接口获取instance\_id参数值。 |
| name | String | 是 | PROC-EFxxxx | 表单code，进入表单编辑页面，最下方可查看。 ![[development-retrieves-custom-crm-forms-from-the-id-list_p511616.png]] |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| result\_list | ObjectDataInstanceVo[] |  | 实例数据。 |
| creator\_nick | String | 张xx | 记录创建人的昵称。 |
| gmt\_modified | String | 2019-12-25 15:33:12 | 修改时间。 |
| creator\_userid | String | user01 | 创建人的用户userId。 |
| instance\_id | String | INST\_XX | 数据ID。 |
| data | String | {\"contact\_name\":\"李四\"} | 数据内容。 |
| extend\_data | String | {\"field\_1\":\"CRM\"} | 扩展数据内容。 |
| gmt\_create | String | 2019-12-25 15:33:12 | 记录创建时间。 |
| object\_type | String | crm\_follow\_record | 数据类型。 |
| permission | DataPermissionVo |  | 数据权限信息。 |
| participant\_userid\_list | String[] | ["user01","user02"] | 协同人用户userId列表。 |
| owner\_userid\_list | String[] | ["user01","user02"] | 负责人用户userId列表。 |
| proc\_out\_result | String | agree | 审批结果。 |
| proc\_inst\_status | String | COMPLETE | 审批状态。 |
| errcode | Number | 0 | 返回码。 |
| errmsg | String | ok | 返回码描述。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/crm/objectdata/list?access_token=ACCESS_TOKEN
```

请求正文

```json
{
        "name":"PROC-EFxxxx",
        "current_operator_userid":"user01",
        "data_id_list":"INST_XX1,INST_XX2"
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/crm/objectdata/list");
OapiCrmObjectdataListRequest req = new OapiCrmObjectdataListRequest();
req.setCurrentOperatorUserid("user01");
req.setDataIdList("INST_XX1,INST_XX2");
req.setName("PROC-EFxxxx");
OapiCrmObjectdataListResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```
{
    "errcode": 0,
    "errmsg":"ok",
    "result_list": [
        {
            "creator_userid": "015605066814171",
            "data": "{\"contract_no\":{\"value\":\"HT2022042100000003\"},\"contract_name\":\"1\",\"contract_related_customer\":{\"extendValue\":\"{\\\"quote\\\":1,\\\"list\\\":[{\\\"bizType\\\":\\\"crm_customer_personal\\\",\\\"instanceId\\\":\\\"IGpNsR_mTtuKqx7fGienmg04931650374020\\\"}]}\",\"value\":\"[\\\"82\\\"]\"},\"contract_amount\":2.0,\"contract_status\":{\"extendValue\":\"{\\\"extension\\\":{\\\"editFreeze\\\":true},\\\"label\\\":\\\"已作废\\\",\\\"key\\\":\\\"option_canceled\\\"}\",\"value\":\"已作废\"},\"DDDateField-KI5RLXW2\":1650470400000}",
            "gmt_create": "2022-04-21 10:06:55",
            "gmt_modified": "2022-04-21 10:06:55",
            "instance_id": "INST_XX1",
            "permission": {
                "owner_userid_list": [],
                "participant_userid_list": []
            },
            "proc_inst_status": "RUNNING"
        },
        {
            "creator_userid": "015605066814171",
            "data": "{\"contract_no\":{\"value\":\"HT2022031700000001\"},\"contract_name\":\"1\",\"contract_related_customer\":{\"extendValue\":\"{\\\"quote\\\":1,\\\"list\\\":[{\\\"bizType\\\":\\\"crm_customer_personal\\\",\\\"instanceId\\\":\\\"45a1ade5-9aea-4767-a7be-5592fc8b49ab\\\"}]}\",\"value\":\"[\\\"好的111\\\"]\"},\"contract_amount\":1.0,\"contract_status\":{\"extendValue\":\"{\\\"extension\\\":{\\\"editFreeze\\\":true},\\\"label\\\":\\\"未开始\\\",\\\"key\\\":\\\"option_not_started\\\"}\",\"value\":\"未开始\"},\"DDDateField-KI5RLXW2\":1647446400000}",
            "gmt_create": "2022-03-17 16:34:10",
            "gmt_modified": "2022-03-17 16:34:10",
```