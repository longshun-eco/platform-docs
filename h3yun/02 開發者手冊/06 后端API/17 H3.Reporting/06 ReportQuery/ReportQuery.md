---
title: "ReportQuery"
source: "https://help.h3yun.com/contents/540/446.html"
category: "開發者手冊 / 后端API / H3.Reporting / ReportQuery"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : ReportQuery
说明 : 报表 分析查询 属性 : 

| 名称 | 说明 |
| --- | --- |
| CommandFactory | 访问数据库用的接口 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| DatabaseConnString | 数据库连接字符串 |
| DatabaseType | 数据库类型 |
| Engine | 引擎 |


构造方法名称 : #ctor(H3.Clusterware.EngineConfig,H3.Organization.IOrganization,H3.DataModel.IBizObjectManager)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.IEngine)

| 参数 | 说明 |
| --- | --- |
| "iEngine" | |
| 返回值 |  |
| |  |


方法名称 : QueryTableCount(System.String,H3.Reporting.ReportFilter\[\],H3.Reporting.ReportWidgetColumn\[\],System.Collections.Generic.List{System.String},System.Collections.Generic.List{H3.Data.Database.Parameter},H3.Reporting.ReportSource,System.Boolean,System.String)

| 参数 | 说明 |
| --- | --- |
| "tableName" | 表名 |
| "reportFilters" | 过滤项 |
| "columns" | 列 |
| "widgetCondition" | 生成table时产生的过滤条件 |
| "widgetParameters" | 生成table时产生的过滤条件的值 |
| "reportSource" | 数据源 |
| "groupbyObjectId" | 根据group by objectid获取count |
| "groupby" | groupby列名 |
| 返回值 |  |
| |  |


方法名称 : QueryTable(System.String,H3.Reporting.ReportWidgetColumn\[\],H3.Reporting.ReportWidgetColumn\[\],H3.Reporting.ReportFilter\[\],System.Collections.Generic.Dictionary{System.String,System.String}@,System.Collections.Generic.List{H3.Reporting.ReportWidgetColumn}@,System.Int32,System.Int32,System.Int32@,System.Collections.Generic.List{System.String},System.Collections.Generic.List{H3.Data.Database.Parameter},H3.Reporting.ReportSource,System.Boolean,H3.Reporting.WidgetType,System.Boolean,System.String)

| 参数 | 说明 |
| --- | --- |
| "tableName" | 表名称 |
| "columns" | 列集合 |
| "sortColumns" | 排序字段集合 |
| "filters" | 过滤对象集合 |
| "unitAndAssociationTable" | 组织结构和关联表集合 |
| "typeChangedColumns" | 类型该表列集合 |
| "start" | 分页起始行 |
| "end" | 分页结束行 |
| "count" | 记录总数 |
| "widgetCondition" | 生成table时产生的过滤条件 |
| "widgetParameters" | 生成table时产生的过滤条件的值 |
| "reportSource" | 报表数据源 |
| "showStatistical" | 是否显示统计字段 |
| "type" | 报表类型 |
| "countGroupbyObjectId" | 根据group by objectid获取count |
| "groupBy" | 排序字段 |
| 返回值 |  |
| |  |


方法名称 : QueryTable(System.String,H3.Reporting.ReportWidgetColumn\[\],H3.Reporting.ReportWidgetColumn\[\],H3.Reporting.ReportFilter\[\],System.Collections.Generic.Dictionary{System.String,System.String}@,System.Collections.Generic.List{H3.Reporting.ReportWidgetColumn}@,System.Collections.Generic.List{System.String},System.Collections.Generic.List{H3.Data.Database.Parameter},H3.Reporting.ReportSource,System.Int32,System.Int32,System.Boolean,H3.Reporting.WidgetType,System.Boolean,System.String)

| 参数 | 说明 |
| --- | --- |
| "tableName" | 表名称 |
| "columns" | 列集合 |
| "sortColumns" | 排序字段集合 |
| "filters" | 过滤对象集合 |
| "unitAndAssociationTable" | 组织结构和关联表集合 |
| "typeChangedColumns" | 类型该表列集合 |
| "widgetCondition" | 生成table时产生的过滤条件 |
| "widgetParameters" | 生成table时产生的过滤条件的值 |
| "reportSource" | 报表数据源 |
| "start" | 起始行 |
| "end" | 结束行 |
| "showStatistical" | 是否显示统计字段 |
| "type" | 报表类型 |
| "countGroupbyObjectId" | 根据group by objectid获取count |
| "groupBy" | 排序字段 |
| 返回值 |  |
| |  |


方法名称 : GetTypeChangedColumn(H3.Reporting.ReportWidgetColumn,System.Type)

| 参数 | 说明 |
| --- | --- |
| "column" | |
| "sqltype" | |
| 返回值 |  |
| |  |


方法名称 : GetFormatValue(System.Double,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "v" | 值 |
| "format" | 格式 |
| "isChart" | 是图表 |
| 返回值 |  |
| |  |


方法名称 : GetTablePageParameter(H3.Reporting.ReportFilter\[\],H3.Reporting.ReportWidgetColumn\[\],System.Collections.Generic.List{System.String}@,System.String,System.String@,System.Collections.Generic.List{System.String},System.Collections.Generic.List{H3.Data.Database.Parameter},H3.Reporting.ReportSource,System.Boolean,System.String)

| 参数 | 说明 |
| --- | --- |
| "filters" | 过滤项 |
| "columns" | 列集合 |
| "conditions" | 过滤条件 |
| "oldTableName" | 原表明 |
| "newTableName" | 新表明 |
| "widgetCondition" | 生成table时产生的过滤参数 |
| "widgetParameters" | 生成table时产生的过滤参数的值 |
| "reportSource" | 报表数据源 |
| "countGroupbyObjectId" | 根据group by objectid获取count |
| "groupby" | 排序字段 |
| 返回值 |  |
| |  |


方法名称 : GetDbTypeByParameterType(H3.Reporting.FilterType)

| 参数 | 说明 |
| --- | --- |
| "FilterType" | 过滤类型 |
| 返回值 |  |
| |  |


方法名称 : GetParameterValue(H3.Reporting.ReportFilter,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "reportFilter" | 报表过滤对象 |
| "isSqlWhere" | 是否附加where条件过滤 |
| 返回值 |  |
| |  |


方法名称 : GetQueryTableGroupbyTableName(System.String,System.String,System.String,System.String,System.Int32,System.Int32,System.Collections.Generic.List{System.String},H3.Reporting.ReportWidgetColumn\[\],H3.Reporting.ReportWidgetColumn\[\],H3.Reporting.ReportSource)

| 参数 | 说明 |
| --- | --- |
| "newTableName" | |
| "newGroupby" | |
| "tempgroupby" | |
| "tempguid" | |
| "f" | |
| "t" | |
| "conditions" | |
| "columns" | |
| "sortColumns" | |
| "reportSource" | |
| 返回值 |  |
| |  |


方法名称 : GetOrder(H3.Reporting.ReportWidgetColumn\[\],H3.Reporting.ReportWidgetColumn\[\],H3.Reporting.ReportSource)

| 参数 | 说明 |
| --- | --- |
| "columns" | 列 |
| "sortColumns" | 排序列 |
| "reportSource" | 数据源 |
| 返回值 |  |
| |  |


方法名称 : BuildStatisticalColumnStr(H3.Reporting.ReportWidgetColumn\[\],H3.Reporting.ReportSource)

| 参数 | 说明 |
| --- | --- |
| "columns" | 列 |
| "reportSource" | 数据源 |
| 返回值 |  |
| |  |


方法名称 : BuildColumnString(H3.Reporting.ReportWidgetColumn\[\],H3.Reporting.ReportSource)

| 参数 | 说明 |
| --- | --- |
| "columns" | 列集合 |
| "reportSource" | 数据源 |
| 返回值 |  |
| |  |


方法名称 : GetOriginalField(System.String,H3.Reporting.ReportSource,H3.Reporting.ReportWidgetColumn)

| 参数 | 说明 |
| --- | --- |
| "field" | |
| "reportSource" | |
| "column" | |
| 返回值 |  |
| |  |


方法名称 : GetTableColumns(System.String,System.Collections.Generic.Dictionary{System.String,H3.Reporting.ReportWidgetColumn},System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "tableName" | 表名 |
| "reportWidgetColumns" | 列 |
| "onlySortableItems" | 仅获取可排序的项 |
| 返回值 |  |
| |  |


方法名称 : GetSqlColumns(System.String)

| 参数 | 说明 |
| --- | --- |
| "sql" | |
| 返回值 |  |
| |  |


方法名称 : GetSourceColumns(H3.Reporting.ReportWidget,H3.Reporting.ReportSource,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "reportWidget" | widget |
| "reportSource" | 数据源 |
| "onlySortableItems" | 仅获取排序项 |
| 返回值 |  |
| |  |


方法名称 : CheckSQLWhere(System.String,H3.Reporting.ReportWidgetColumn\[\],System.String@,System.Collections.Generic.List{System.String}@)

| 参数 | 说明 |
| --- | --- |
| "oldSql" | sql |
| "columns" | 列 |
| "newSql" | 新sql |
| "beReplaceItems" | 替代的项 |
| 返回值 |  |
| |  |


方法名称 : GetSourceColumns(H3.Reporting.ReportWidgetSimpleBoard,H3.Reporting.ReportSource)

| 参数 | 说明 |
| --- | --- |
| "simpleBoard" | 简易看板 |
| "reportSource" | 数据源 |
| 返回值 |  |
| |  |


方法名称 : GetSchemaCodeNameDisplayName(H3.Reporting.ReportWidget,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "reportWidget" | widget |
| "onlySortableItems" | 仅获取可排序的项 |
| 返回值 |  |
| |  |


方法名称 : GetSchemaCodeNameDisplayName(H3.Reporting.ReportWidgetSimpleBoard)

| 参数 | 说明 |
| --- | --- |
| "simpleBoard" | 简易看板的widget |
| 返回值 |  |
| |  |


方法名称 : GetSourceColumnsBySchemaCode(System.String,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.Dictionary{System.String,H3.Reporting.ReportWidgetColumn}},System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 编码 |
| "schemaCodeNameDisplayName" | column显示名称 |
| "onlySortableItems" | 仅获取可排序的项 |
| 返回值 |  |
| |  |


方法名称 : GetSoucrColumnsSummaryBySchemaCode(System.String,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.Dictionary{System.String,System.String}})

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 编码 |
| "schemaCodeNameDisplayName" | column显示名称 |
| 返回值 |  |
| |  |


方法名称 : GetTableName(System.String)

| 参数 | 说明 |
| --- | --- |
| "SchemaCode" | 编码 |
| 返回值 |  |