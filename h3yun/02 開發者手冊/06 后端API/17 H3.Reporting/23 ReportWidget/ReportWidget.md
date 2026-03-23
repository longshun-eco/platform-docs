---
title: "ReportWidget"
source: "https://help.h3yun.com/contents/557/513.html"
category: "開發者手冊 / 后端API / H3.Reporting / ReportWidget"
updated: 2025-12-21
tags:
  - h3yun
  - 開發者手冊
---
类名 : ReportWidget
说明 : 报表配置 属性 : 

| 名称 | 说明 |
| --- | --- |
| Code | 编码 |
| DisplayName | 显示名称 |
| WidgetType | 报表类型 |
| ReportSourceId | 数据源的ObjectId |
| Series | 系列 |
| Categories | 分类 |
| Columns | 源列 @报表类型(ReportType)是明细表时，这里是报表的展示列 @报表类型(ReportType)是汇总表时，这里记录的是统计字段 |
| FilterColumns | 源列 @报表过滤数据源(数据源过滤的功能未加) |
| SortColumns | 排序字段 |
| PropertyName\_Exportable | 属性名称 |
| Exportable | 可导出 |
| PropertyName\_Layout | 属性名称 |
| Layout | 布局，1行1列或1行2列 |
| LinkageReports | 联动报表 |
| SourceFilters | 数据源过滤 |
| ReportWidgetSimpleBoard | 简易看板 |
| PropertyName\_SimpleBoardRowNumber | 属性名称 |
| SimpleBoardRowNumber | 简易看板横向个数 |
| PropertyName\_SimpleBoardColumnNumber | 属性名称 |
| SimpleBoardColumnNumber | 简易看板横向个数 |
| PropertyName\_DefaultSeriesData | 属性名称 |
| DefaultSeriesData | 默认系列数据 |
| PropertyName\_DefaultCategorysData | 属性名称 |
| DefaultCategorysData | 默认分类数据 |
| FrozenHeaderType | 冻结表头，仅汇总表可用 |
| PropertyName\_XAxisUnit | X轴单位 属性名称 |
| XAxisUnit | X轴单位 |
| PropertyName\_YAxisUnit | 属性名称 |
| YAxisUnit | Y轴单位 |
| PropertyName\_IsCustom | 属性名称 |
| IsCustom | 是自开发的 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 物理表 |
| PropertyName\_Code | 属性名称 |
| PropertyName\_DisplayName | 属性名称 |
| PropertyName\_WidgetType | 属性名称 |
| PropertyName\_ReportSourceId | 属性名称 |
| PropertyName\_Series | 属性名称 |
| PropertyName\_Categorys | 属性名称 |
| PropertyName\_Columns | 属性名称 |
| PropertyName\_FilterColumns | 属性名称 |
| PropertyName\_SortColumns | 属性名称 |
| PropertyName\_LinkageReports | 属性名称 |
| PropertyName\_SourceFilters | 属性名称 |
| \_SourceFilters | 数据源过滤 |
| PropertyName\_ReportWidgetSimpleBoard | 属性名称 |
| PropertyName\_FrozenHeaderType | 报表类型名称 |


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