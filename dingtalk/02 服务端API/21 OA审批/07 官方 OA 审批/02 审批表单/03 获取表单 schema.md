---
title: "获取表单 schema新版SDK"
source: "https://open.dingtalk.com/document/development/obtain-the-form-schema"
category: "服务端API / OA审批 / 官方 OA 审批 / 审批表单"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-obtain-the-form-schema_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-the-form-schema_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-11 调用本接口，通过 processCode，获取对应表单的 schema 信息。

本接口获取的部分信息如下图所示。

![[development-obtain-the-form-schema_O1CN01FCBFTJ25wjHBznqCI_!!6000000007591-0-tps-1235-967.jpg]]

**说明**

三方企业应用没有权限获取组织内的表单schema。

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | 工作流模板读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=workflow_1.0%23QuerySchemaByProcessCode) |
| 第三方企业应用 | 支持 | 工作流模板读权限 | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=workflow_1.0%23QuerySchemaByProcessCode) |
| 第三方个人应用 | 暂不支持 | 工作流模板读权限 | 暂不支持 |

## 请求方法

```
GET /v1.0/workflow/forms/schemas/processCodes?processCode=String HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过以下获取：   * 企业内部应用，调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 * 第三方企业应用，调用[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口获取。 |

## Query参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| processCode | String | 是 | 表单的唯一码。 |
| appUuid | String | 否 | 应用搭建隔离信息 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| result | Object | 返回结果详情。 |
| creatorUserId | String | 创建人 userId。 |
| appUuid | String | 表单应用 uuid 或者 corpId。 |
| formCode | String | 表单的唯一码。 |
| formUuid | String | 表单 uuid。 |
| name | String | 表单名称。 |
| memo | String | 说明文案。 |
| ownerIdType | String | 数据归属者的 id 类型，取值：   * orgId：企业 * cid：群 * uid：人 |
| schemaContent | Object | 表单 schema 详情。 |
| title | String | 表单名称。 |
| icon | String | 图标 |
| items | Array | 控件列表。 |
| componentName | String | 控件类型，取值：   * TextField：单行输入框 * TextareaField：多行输入框 * NumberField：数字输入框 * DDSelectField：单选框 * DDMultiSelectField：多选框 * DDDateField：日期控件 * DDDateRangeField：时间区间控件 * TextNote：文字说明控件 * PhoneField：电话控件 * DDPhotoField：图片控件 * MoneyField：金额控件 * TableField：明细控件 * DDAttachment：附件 * InnerContactField：联系人控件 * DepartmentField：部门控件 * RelateField：关联审批单 * AddressField：省市区控件 * StarRatingField：评分控件 * FormRelateField：关联控件 |
| props | Object | 控件属性。 |
| id | String | 控件 id。 |
| tableViewMode | String | 明细填写方式，枚举值：   * list：列表 * table：表格 |
| label | String | 控件名称。 |
| bizAlias | String | 控件业务自定义别名。 |
| required | Boolean | 是否必填，取值：   * true：是 * false：否 |
| placeholder | String | 占位符。 |
| options | Array of String | 单选框选项值。 |
| appId | Long | ISV 微应用 appId，用于ISV身份权限识别，ISV可获得相应数据。 |
| durationLabel | String | 兼容字段。 |
| pushToCalendar | Integer | 是否推送管理日历(DDDateRangeField, 该属性为兼容保留)，取值：   * 1：推送 * 0：不推送 |
| align | String | textNote的样式，取值：   * top：顶部 * middle：中部 * bottom：底部 |
| statField | Array | 需要计算总和的明细组件。 |
| id | String | id 值。 |
| label | String | 名称。 |
| upper | Boolean | 是否大写，取值：   * true：是 * false：否 |
| unit | String | 单位。 |
| hideLabel | Boolean | 加班套件4.0新增，加班明细是否隐藏标签，取值：   * true：是 * false：否 |
| objOptions | Array | 选项内容列表，提供给业务方更多的选择器操作。 |
| value | String | 选项值。 |
| format | String | 时间格式(DDDateField和DDDateRangeField)。 |
| pushToAttendance | Boolean | 是否推送到考勤, 子类型(DDSelectField)，取值：   * true：是 * false：否 |
| labelEditableFreeze | Boolean | label是否可修改，取值：   * true：不可修改 * false：可修改 |
| push | Object | 同步到考勤, 表示是否设置为员工状态。 |
| pushSwitch | Integer | 开启状态，取值：   * 1：开启 * 0：关闭 |
| pushTag | String | 状态显示名称 |
| attendanceRule | Integer | 考勤类型，取值：   * 1：请假 * 2：出差 * 3：加班 * 4：外出 |
| commonBizType | String | common field的commonBizType。 |
| requiredEditableFreeze | Boolean | 必填是否可修改，取值：   * true：不可修改 * false：可修改 |
| unit | String | 数字组件/日期区间组件单位属性。 |
| extract | Boolean | 套件值是否打平，取值：   * true：是 * false：否 |
| link | String | 说明文案的链接地址。 |
| payEnable | Boolean | 是否有支付属性，取值：   * true：是 * false：否 |
| hidden | Boolean | 加班套件4.0新增 加班明细是否隐藏，取值：   * true：是 * false：否 |
| bizType | String | 业务套件类型。 |
| staffStatusEnabled | Boolean | 是否开启员工状态，取值：   * true：是 * false：否 |
| actionName | String | 加班套件4.0新增 加班明细名称。 |
| attendTypeLabel | String | 请假、出差、外出、加班类型标签。 |
| childFieldVisible | Map<String, Boolean> | 套件内子组件可见性，取值：   * true：是 * false：否 |
|  | Boolean | 套件内子组件可见性，取值：   * true：是 * false：否 |
| notPrint | String | 是否参与打印，取值：   * 1：不打印 * 0：打印 |
| verticalPrint | Boolean | 明细打印排版方式，取值：   * true：纵向 * false：横向 |
| duration | Boolean | 是否自动计算时长，取值：   * true：是 * false：否 |
| holidayOptions | Array of Object | 兼容出勤套件类型。 |
| useCalendar | Boolean | 是否使用考勤日历，取值：   * true：是 * false：否 |
| hiddenInApprovalDetail | Boolean | textnote在详情页是否隐藏，取值：   * true：是 * false：否 |
| disabled | Boolean | 是否可编辑，取值：   * true：是 * false：否 |
| asyncCondition | Boolean | 套件是否开启异步获取分条件规则，取值：   * true：是 * false：否 |
| behaviorLinkage | Array | 表单关联控件列表。 |
| value | String | 控件值。 |
| targets | Array | 关联控件列表。 |
| fieldId | String | 字段 id。 |
| behavior | String | 行为。 |
| showAttendOptions | Boolean | 兼容出勤套件类型。 |
| notUpper | String | 是否需要大写，默认是需要，取值：   * 1：不需要 * 0 或空：需要 |
| fieldsInfo | String | 关联表单中的fields存储 |
| eSign | Boolean | e签宝专用标识。 |
| mainTitle | String | 加班套件4.0新增 加班明细描述。 |
| formula | String | 公式。 |
| choice | Integer | 内部联系人choice，取值：   * 1：多选 * 0：单选 |
| children | Array | 子控件列表。 |
| componentName | String | 子控件类型，取值：   * TextField：单行输入框 * TextareaField：多行输入框 * NumberField：数字输入框 * DDSelectField：单选框 * DDMultiSelectField：多选框 * DDDateField：日期控件 * DDDateRangeField：时间区间控件 * TextNote：文字说明控件 * PhoneField：电话控件 * DDPhotoField：图片控件 * MoneyField：金额控件 * DDAttachment：附件 * InnerContactField：联系人控件 * DepartmentField：部门控件 * RelateField：关联审批单 * AddressField：省市区控件 * StarRatingField：评分控件 * FormRelateField：关联控件 |
| props | Object | 子控件属性 |
| id | String | 控件id |
| label | String | 控件名称 |
| bizAlias | String | 控件业务别名 |
| required | Boolean | 是否必填 |
| options | Array of String | 单选框选项值。 |
| icon | String | 图标。 |
| appType | Integer | 表单类型。 |
| bizType | String | 代表表单业务含义的类型。 |
| engineType | Integer | 引擎类型，取值：   * 1：页面 * 0：表单 |
| status | String | 状态，取值：   * PUBLISHED：启用 * INVALID：停用 * SAVED：草稿 |
| listOrder | Integer | 排序 id。 |
| customSetting | String | 业务自定义设置数据。 |
| procType | String | 目标类型，取值：   * inner：内部 * outer：外部 * customer：自定义 |
| visibleRange | String | 可见范围类型。 |
| gmtCreate | String | 创建时间的时间戳。 |
| gmtModified | String | 修改时间的时间戳。 |

## 示例

**请求示例**

HTTP

```
GET /v1.0/workflow/forms/schemas/processCodes?processCode=PROC-17428B8C-6C60-xxxx-924C-64F1037AE067&appUuid=SWAPP-abcd-example HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:f31f78b59d9438b9859e40xxxx9882f0
Content-Type:application/json
```

Java

```
// This file is auto-generated, don't edit it. Thanks.
```

Python

```
# -*- coding: utf-8 -*-
```

PHP

```
php</code
```

Go

```
// This file is auto-generated, don't edit it. Thanks.
```

Node.js

```
// This file is auto-generated, don't edit it
```

C#

```
// This file is auto-generated, don't edit it. Thanks.
```

**返回示例**

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "result" : {
    "creatorUserId" : "26652461xxxx5992",
    "appUuid" : "xxxx",
    "formCode" : "PROC-17428B8C-6C60-470E-xxxx-64F1037AE067",
    "formUuid" : "FORM-28215C3E-00E3-4118-xxxx-4091F828AF2F",
    "name" : "示例模板",
    "memo" : "xxxx",
    "ownerIdType" : "orgId",
    "schemaContent" : {
      "title" : "示例模板",
      "icon" : "common",
      "items" : [ {
        "componentName" : "TextField",
        "props" : {
          "id" : "TextField-K2AD4O5B",
          "label" : "单行输入框",
          "bizAlias" : "我的单行输入框",
```

## 错误码

|  |  |  |  |
| --- | --- | --- | --- |
| HttpCode | 错误码 | 错误信息 | 说明 |
| 400 | formNotExist | 审批表单模板不存在 | 审批表单模板不存在 |
| 400 | invalidParameter | 参数错误，具体可能为：企业ID、审批模板code等参数错误 | 参数错误，具体可能为：企业ID、审批模板code等参数错误 |
| 400 | noPermission | 没有权限访问当前表单 | 权限校验失败 |
| 400 | aflowProcessCodeIsError | 获取审批模板失败或审批模板已被删除 | 获取审批模板失败或审批模板已被删除 |
| 400 | internalError | %s | 系统内部异常 |
| 500 | systemError | 系统异常 | 系统异常 |