---
title: "ReportFilter"
source: "https://help.h3yun.com/contents/551/493.html"
category: "開發者手冊 / 后端API / H3.Reporting / ReportFilter"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : ReportFilter
说明 : 报表过滤 属性 : 

| 名称 | 说明 |
| --- | --- |
| ColumnCode | 列编码（报表数据源内唯一） |
| ColumnName | 列名称(数据库原始的) |
| DisplayName | 显示名称 |
| PropertyName\_FilterType | 属性名称 |
| FilterType | 参数类型 |
| PropertyName\_FilterValue | 属性名称 |
| FilterValue | 参数值 ParameterType=时间：1=当天；2=本周；3=本月;4=本季度；5=本年度; ParameterType=组织类型：1=本人;2=本部门;3=所有 |
| PropertyName\_DefaultValue | 属性名称 |
| DefaultValue | 默认值 |
| PropertyName\_ColumnType | 属性名称 |
| ColumnType | 列类型 |
| AssociationSchemaCode | 如果该字段是一个关联字段，那么这里记录关联的类型，有两种：固定关联某一个Schema下面的某个对象，如果是固定的，那么这里记录的是SchemaCode，如果是变化的，那么这里记录是哪个字段记录SchemaCode |
| AssociationField | 关联字段 |
| AssociationFilter | 关联查询过滤规则 |
| PropertyName\_OrganizationType | 属性名称 |
| OrganizationType | 默认值 |
| PropertyName\_AllowNull | 属性名称 |
| AllowNull | 允许为空 |
| PropertyName\_Visible | 属性名称 |
| Visible | 是否显示 |
| PropertyName\_IsSqlWhere | 属性名称 |
| IsSqlWhere | 是否显示 |
| PropertyName\_IsCustom | 属性名称 |
| IsCustom | 是自开发的 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_ColumnCode | 属性名称 |
| PropertyName\_ColumnName | 属性名称 |
| PropertyName\_DisplayName | 属性名称 |
| PropertyName\_AssociationSchemaCode | 属性名称 |
| PropertyName\_AssociationField | 属性名称 |
| PropertyName\_AssociationFilter | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |