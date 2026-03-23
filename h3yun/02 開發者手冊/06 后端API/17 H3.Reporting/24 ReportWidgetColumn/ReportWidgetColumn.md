---
title: "ReportWidgetColumn"
source: "https://help.h3yun.com/contents/558/516.html"
category: "開發者手冊 / 后端API / H3.Reporting / ReportWidgetColumn"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : ReportWidgetColumn
说明 : 报表数据源源列 属性 : 

| 名称 | 说明 |
| --- | --- |
| ColumnCode | 列编码（报表数据源内唯一） |
| ColumnName | 列名称(数据库原始的) |
| DisplayName | 显示名称,对于数据模型类型的报表，显示名称直接取porperty的 |
| ColumnType | 数据类型 |
| Sortable | 是否排序字段 |
| AssociationSchemaCode | 如果该字段是一个关联字段，那么这里记录关联的类型，有两种：固定关联某一个Schema下面的某个对象，如果是固定的，那么这里记录的是SchemaCode，如果是变化的，那么这里记录是哪个字段记录SchemaCode |
| Ascending | 为升序 |
| FunctionType | 汇总类型 |
| NotShowStatistic | 不显示汇总 |
| ColumnDataFormat | 汇总类型 |
| Format | 显示格式(yyyy-MM-dd,yy-MM-dd,yy-MM,yy)(%,‰),(dot;8) |
| Formula | 计算规则表达式 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名 |
| DefaultCountCode | 默认计算字段编码 |
| DefaultCountDisplayName | 默认计算字段名称 |
| DefaultTrue | 默认true的值 |
| DefaultFalse | 默认false的值 |
| PropertyName\_ColumnCode | 属性名称 |
| PropertyName\_ColumnName | 属性名称 |
| PropertyName\_DisplayName | 属性名称 |
| PropertyName\_ColumnType | 属性名称 |
| PropertyName\_Sortable | 属性名称 |
| PropertyName\_AssociationSchemaCode | 属性名称 |
| PropertyName\_Ascending | 属性名称 |
| PropertyName\_FunctionType | 属性名称 |
| PropertyName\_NotShowStatistic | 属性名称 |
| PropertyName\_ColumnDataFormat | 属性名称 |
| PropertyName\_Format | 属性名称 |
| PropertyName\_Formula | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |