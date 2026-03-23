---
title: "创建CRM自定义对象数据旧版SDK"
source: "https://open.dingtalk.com/document/development/dingtalk-paas-master-create-custom-crm-object-data"
category: "服务端API / 客户管理（官方CRM） / 自定义对象"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-dingtalk-paas-master-create-custom-crm-object-data_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dingtalk-paas-master-create-custom-crm-object-data_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23调用本接口，向自定义表单内创建对象数据。

**重要**

本接口只能创建纯表单数据，不能用于创建流程表单数据。

调用本接口，可创建CRM自定义对象数据。接口调用效果与下图操作实现效果一致。

![[development-dingtalk-paas-master-create-custom-crm-object-data_p511607.png]]

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 是 | CRM自定义对象数据的接口写入权限 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=dingtalk.oapi.crm.objectdata.customobject.create) |
| 第三方企业应用 | 否 | — | — |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/crm/objectdata/customobject/create`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | dc73axxxx | 调用该接口的应用凭证，通过[获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| instance | ObjectDataInstanceVo | 是 |  | 自定义对象数据。 |
| creator\_userid | String | 是 | user01 | 创建人的用户userId。 |
| data | String | 是 | {"TextField-xxxxxx":"李四"} | 数据内容，JSON格式字符串。传参格式详见[自定义控件字段格式说明V1](/document/development/custom-control-field-format-description-v1)。 |
| extend\_data | String | 否 | {"field\_1":"CRM"} | 扩展数据内容。 |
| permission | DataPermissionVo | 否 |  | 权限。 |
| participant\_userids | String[] | 否 | ["user01","user02"] | 协同人的用户userId。 |
| form\_code | String | 是 | PROC-A1xxxx | 自定义对象表单code，进入自定义表单编辑页面，最下方可查看。  ![[development-dingtalk-paas-master-create-custom-crm-object-data_p511603.png]] |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| result | ObjectDataCreateDto |  | 返回结果。 |
| instance\_id | String | INST\_XX | 自定义对象数据ID。 |
| success | Boolean | true | 是否执行成功。   * **true**：成功 * **false**：失败 |
| errcode | Number | 0 | 返回码。 |
| errmsg | String | ok | 返回码描述。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/crm/objectdata/customobject/create?access_token=ACCESS_TOKEN
```

请求正文

```json
{
    "instance": {
        "extend_data": {
            "field_1":"CRM"
        },
        "data": {
            "TextField-xxxxxx":"李xx"
        },
        "creator_userid": "user01",
        "permission": {
            "participant_userids": [
                "user01",
                "user02"
            ]
        },
        "form_code": "PROC-A1xxxx"
    }
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/crm/objectdata/customobject/create");
OapiCrmObjectdataCustomobjectCreateRequest req = new OapiCrmObjectdataCustomobjectCreateRequest();
ObjectDataInstanceVo objectDataInstanceVo = new ObjectDataInstanceVo();
objectDataInstanceVo.setCreatorUserid("user01");
objectDataInstanceVo.setData("{\"TextField-xxxxxx\":\"李xx\"}");
objectDataInstanceVo.setExtendData("{\"field_1\":\"CRM\"}");
DataPermissionVo dataPermissionVo = new DataPermissionVo();
dataPermissionVo.setParticipantUserids(Arrays.asList("user01", "user02"));
objectDataInstanceVo.setPermission(dataPermissionVo);
objectDataInstanceVo.setFormCode("PROC-A1xxxx");
req.setInstance(objectDataInstanceVo);
OapiCrmObjectdataCustomobjectCreateResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
    "result": {
        "instance_id": "INST_XX"
    },
    "errcode": 0,
    "success": true,
    "errmsg": "ok"
}
```