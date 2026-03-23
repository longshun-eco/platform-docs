---
title: "获取数据表单schema新版SDK"
source: "https://open.dingtalk.com/document/development/api-premiumgetformschema"
category: "服务端API / OA审批 / 高级版专享接口 / 数据表单 / 表单模板"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-premiumgetformschema_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-premiumgetformschema_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-11 调用本接口，通过数据表单code，获取对应表单的schema信息。

### 特别提醒

**说明**

当前接口为OA高级版专享接口，升级OA高级版可用，可满足更高级的开发需求，响应个性化的业务场景，查看全部[专享OpenAPI](/document/development/description-of-new-oa-approval-premium-exclusive-openapi-and-solutions)。

### 接口功能介绍

例如，调用本接口获取数据表单schema，接口调用效果如下图所示。

![[development-api-premiumgetformschema_O1CN01HmRvSB1hy3uqwtAdX_!!6000000004345-0-tps-1643-822.jpg]]

## 权限

要调用此API，需要以下权限之一。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持 | 权限 | API Explorer调试 |
| 企业内部应用 | 支持 | OA审批工作流读写权限（OA高级版专享） | [API Explorer](https://open-dev.dingtalk.com/apiExplorer#/?devType=org&api=workflow_1.0%23PremiumGetFormSchema) |
| 第三方企业应用 | 暂不支持 | 暂不支持 | 暂不支持 |
| 第三方个人应用 | 暂不支持 | 暂不支持 | 暂不支持 |

## 请求方法

```
GET /v1.0/workflow/premium/dataForms/schema/formCodes?processCode=String&appUuid=String HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json
```

## Header参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| x-acs-dingtalk-access-token | String | 是 | 调用该接口的访问凭证，通过调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口获取。 |

## Query参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 描述 |
| processCode | String | 是 | 数据表单模板ID。  通过[OA审批概述-名词解释](/document/development/workflow-overview)获取。 |
| appUuid | String | 否 | 应用搭建隔离信息。在**钉钉管理后台—应用管理—应用编辑页**的URL中查看。 |

## 返回参数

|  |  |  |
| --- | --- | --- |
| 名称 | 类型 | 描述 |
| result | Object | 返回结果详情。 |
| creatorUserId | String | 创建人 userId。 |
| formCode | String | 表单的唯一码。 |
| name | String | 表单名称。 |
| memo | String | 说明文案。 |
| schemaContent | Object | 表单 schema 详情。 |
| title | String | 表单名称。 |
| icon | String | 图标。 |
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
| statField | Array | 需要计算总和的明细组件 |
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
| pushTag | String | 状态显示名称。 |
| attendanceRule | Integer | 考勤类型，取值：   * 1：请假 * 2：出差 * 3：加班 * 4：外出 |
| commonBizType | String | common field的commonBizType。 |
| requiredEditableFreeze | Boolean | 必填是否可修改，取值：   * true：不可修改 * false：可修改 |
| unit | String | 数字组件/日期区间组件单位属性。 |
| extract | Boolean | 套件值是否打平。   * true：是 * false：否 |
| link | String | 说明文案的链接地址。 |
| payEnable | Boolean | 是否有支付属性。   * true：是 * false：否 |
| hidden | Boolean | 加班套件4.0新增 加班明细是否隐藏。   * true：是 * false：否 |
| bizType | String | 业务套件类型。 |
| staffStatusEnabled | Boolean | 是否开启员工状态。   * true：是 * false：否 |
| actionName | String | 加班套件4.0新增 加班明细名称。 |
| attendTypeLabel | String | 请假、出差、外出、加班类型标签。 |
| childFieldVisible | Map<String, Boolean> | 套件内子组件可见性。   * true：是 * false：否 |
|  | Boolean | 套件内子组件可见性，取值：   * true：是 * false：否 |
| notPrint | String | 是否参与打印，取值：   * 1：不打印 * 0：打印 |
| verticalPrint | Boolean | 明细打印排版方式，取值：   * true：纵向 * false：横向 |
| duration | Boolean | 是否自动计算时长，取值：   * true：是 * false：否 |
| holidayOptions | Array of Object | 兼容出勤套件类型。 |
| useCalendar | Boolean | 是否使用考勤日历。   * true：是 * false：否 |
| hiddenInApprovalDetail | Boolean | textnote在详情页是否隐藏。   * true：是 * false：否 |
| disabled | Boolean | 是否可编辑。   * true：是 * false：否 |
| asyncCondition | Boolean | 套件是否开启异步获取分条件规则。   * true：是 * false：否 |
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
| props | Object | 子控件属性。 |
| id | String | 控件id。 |
| label | String | 控件名称。 |
| bizAlias | String | 控件业务别名。 |
| required | Boolean | 是否必填。 |
| options | Array of String | 单选框选项值。 |
| icon | String | 图标。 |
| appType | Integer | 表单类型。 |
| status | String | 状态，取值：   * PUBLISHED：启用 * INVALID：停用 * SAVED：草稿 |
| gmtCreate | String | 创建时间的时间戳。 |
| gmtModified | String | 修改时间的时间戳。 |

## 示例

**返回示例**

```
HTTP/1.1 200 OK
Content-Type:application/json

{
  "result" : {
    "creatorUserId" : "26652461xxxx5992",
    "formCode" : "PROC-17428B8C-6C60-470E-xxxx-64F1037AE067",
    "name" : "示例模板",
    "memo" : "xxxx",
    "schemaContent" : {
      "title" : "示例模板",
      "icon" : "common",
      "items" : [ {
        "componentName" : "TextField",
        "props" : {
          "id" : "TextField-K2AD4O5B",
          "tableViewMode" : "list",
          "label" : "单行输入框",
          "bizAlias" : "我的单行输入框",
          "required" : true,
          "placeholder" : "请输入文字",
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
| 500 | formTypeError | 参数无效，不是纯表单 | 参数无效，不是纯表单 |
| 500 | benefit.status.invalid | 权益校验失败，未开通或过期 | 权益校验失败，未开通或过期 |
| 500 | oaplus.query.limit | 请求过于频繁，稍后重试 | 请求过于频繁，稍后重试 |