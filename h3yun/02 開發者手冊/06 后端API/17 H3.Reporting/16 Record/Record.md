---
title: "Record"
source: "https://help.h3yun.com/contents/550/475.html"
category: "開發者手冊 / 后端API / H3.Reporting / Record"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : Record
说明 : 通用实体类型 属性 : 

| 名称 | 说明 |
| --- | --- |
| Creator | 创建人 |
| CreatedTime | 创建时间 |
| ModifiedBy | 修改人 |
| ModifiedTime | 修改时间 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName\_Creator | 创建人 |
| PropertyName\_CreatedTime | 属性名称 |
| PropertyName\_ModifiedBy | 属性名称 |
| PropertyName\_ModifiedTime | 属性名称 |


方法名称 : GetLeftJoinItem(H3.Data.Database.DatabaseType,System.Collections.Generic.List{H3.Reporting.ReportSourceAssociation},System.Collections.Generic.List{System.String},System.Collections.Generic.HashSet{System.String},H3.DataModel.IBizObjectManager,H3.Acl.DataAclScope)

| 参数 | 说明 |
| --- | --- |
| "dbType" | 数据库类型 |
| "associations" | 关联项 |
| "conditions" | 条件 |
| "allScehamCodes" | 所有相关schema |
| "bizObjectManager" | 对象管理器 |
| "scope" | 权限 |
| 返回值 |  |
| |  |


方法名称 : GetTableCondition(H3.DataModel.IBizObjectManager,System.String,System.Boolean,H3.Acl.DataAclScope,System.Collections.Generic.List{System.String}@,H3.Data.Database.DatabaseType)

| 参数 | 说明 |
| --- | --- |
| "bizObjectManager" | 业务数据管理器 |
| "schemaCode" | 数据源的SchemaCode |
| "isSubSheet" | 是子表 |
| "scope" | 权限对象 |
| "conditions" | 条件字符串 |
| "dbType" | 数据库类型 |
| 返回值 |  |
| |  |


方法名称 : GetChildOrgSql(System.Collections.Generic.List{System.String})

| 参数 | 说明 |
| --- | --- |
| "unitids" | 父部门Id |
| 返回值 |  |
| |  |


方法名称 : GetownDeptCondition(System.String,H3.Data.Database.DatabaseType,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{System.String}},System.String)

| 参数 | 说明 |
| --- | --- |
| "table" | |
| "dbType" | |
| "deptSchemas" | |
| "schemaCode" | |
| 返回值 |  |
| |  |


方法名称 : GetOwnCondition(System.String,H3.Data.Database.DatabaseType,System.String)

| 参数 | 说明 |
| --- | --- |
| "table" | |
| "dbType" | |
| "ownerId" | |
| 返回值 |  |
| |  |


方法名称 : GetStatusCondition(System.String,H3.Data.Database.DatabaseType)

| 参数 | 说明 |
| --- | --- |
| "table" | |
| "dbType" | |
| 返回值 |  |
| |  |


方法名称 : GetFunctionColumnSchemaFields(System.String)

| 参数 | 说明 |
| --- | --- |
| "Sql" | |
| 返回值 |  |
| |  |


方法名称 : IsEqualCode(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "code1" | |
| "code2" | |
| 返回值 |  |
| |  |


方法名称 : ExecuteTableName(H3.DataModel.IBizObjectManager,H3.Organization.IOrganization,H3.Reporting.ReportFilter\[\],H3.Acl.DataAclScope,System.Collections.Generic.List{H3.Reporting.ReportWidgetColumn},System.String,H3.Reporting.ReportSource,H3.Data.Database.DatabaseType,System.Collections.Generic.List{System.String}@,System.Collections.Generic.List{H3.Data.Database.Parameter}@)

| 参数 | 说明 |
| --- | --- |
| "bizObjectManager" | 业务数据管理器 |
| "organizationManager" | 组织机构管理器 |
| "filters" | 过滤条件 |
| "scope" | 权限对象 |
| "columns" | 值列 |
| "schemaCode" | 主数据源的SchemaCode |
| "reportSource" | 数据源对象 |
| "dbType" | 数据库类型 |
| "conditions" | 最后条件 |
| "parameters" | 最后条件的参数 |
| 返回值 |  |
| sql语句中 FROM 到 Where之间的部分 |  |


方法名称 : ContainColumnCommon(H3.Reporting.ReportSource,System.String,H3.DataModel.IBizObjectManager,H3.Organization.IOrganization,H3.Data.Database.DatabaseType,H3.Reporting.ReportFilter\[\],System.String)

| 参数 | 说明 |
| --- | --- |
| "reportSource" | |
| "columnCode" | |
| "bizObjectManager" | |
| "organizationManager" | |
| "dbType" | |
| "filters" | |
| "columnDisplayName" | |
| 返回值 |  |