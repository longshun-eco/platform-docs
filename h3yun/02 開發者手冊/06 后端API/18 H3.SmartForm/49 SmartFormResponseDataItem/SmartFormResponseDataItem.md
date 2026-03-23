---
title: "SmartFormResponseDataItem"
source: "https://help.h3yun.com/contents/609/716.html"
category: "開發者手冊 / 后端API / H3.SmartForm / SmartFormResponseDataItem"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : SmartFormResponseDataItem
说明 : 传递到前端的数据项 属性 : 

| 名称 | 说明 |
| --- | --- |
| Type | 获取或设置数据项的逻辑类型 |
| Visible | 是否可见 |
| Editable | 是否可写 |
| Required | 是否必填 |
| Printable | 是否可打印 |
| Value | 获取或设置数据项的值 |
| DisplayName | 获取或设置数据项的显示名称 |
| DataDictItemValue | ERROR, 没看懂这个字段是怎么用的 |
| ComputationRuleFields | 计算规则关联字段 |
| ComputationRule | 计算规则 |
| DisplayRuleFields | 显示规则字段 |
| DisplayRule | 显示规则 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.SmartForm.SmartFormDataItem,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "dataItem" | 业务数据项 |
| "isFormLocked" | 表单是否被锁定，这个锁定通常是由其他用户签出表单造成的 |
| 返回值 |  |
| |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | |
| 返回值 |  |
| |
 |