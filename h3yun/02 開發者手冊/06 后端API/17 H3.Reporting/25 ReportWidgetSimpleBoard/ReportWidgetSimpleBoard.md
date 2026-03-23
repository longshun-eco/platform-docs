---
title: "ReportWidgetSimpleBoard"
source: "https://help.h3yun.com/contents/559/520.html"
category: "開發者手冊 / 后端API / H3.Reporting / ReportWidgetSimpleBoard"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : ReportWidgetSimpleBoard
说明 : 报表配置 属性 : 

| 名称 | 说明 |
| --- | --- |
| Code | 编码 |
| DisplayName | 显示名称 |
| WidgetType | 报表类型 |
| ReportSourceId | 报表对应的数据源 |
| IsSubSheet | 是否子表字段 |
| Columns | 源列 @报表类型(ReportType)是明细汇总表(Summary)时，这里是报表的展示列 @报表类型(ReportType)是交叉分析表(Cross)时，这里记录的是统计字段 |
| RowIndex | 行号 |
| ColumnIndex | 列号 |
| LinkageReports | 联动报表 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 物理表 |
| PropertyName\_Code | 属性名称 |
| PropertyName\_DisplayName | 属性名称 |
| PropertyName\_WidgetType | 属性名称 |
| PropertyName\_ReportSourceId | 属性名称 |
| PropertyName\_IsSubSheet | 属性名称 |
| PropertyName\_Columns | 属性名称 |
| PropertyName\_RowIndex | 属性名称 |
| PropertyName\_ColumnIndex | 属性名称 |
| PropertyName\_LinkageReports | 属性名称 |


方法名称 : GetKeyNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetKeyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "KeyName" | |
| 返回值 |  |
| |  |


方法名称 : ContainColumn(H3.Reporting.ReportFilter\[\],System.String,H3.Reporting.ReportSource,H3.DataModel.IBizObjectManager,H3.Organization.IOrganization,H3.Data.Database.DatabaseType,System.String)

| 参数 | 说明 |
| --- | --- |
| "filters" | 过滤项 |
| "columnCode" | reportColumn的编码 |
| "reportSource" | 数据源 |
| "bizObjectManager" | 业务数据管理器 |
| "organizationManager" | 组织机构管理器 |
| "dbType" | 数据库类型 |
| "columnDisplayName" | reportColumn的显示名称 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |
 |