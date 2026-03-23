---
title: "Parser"
source: "https://help.h3yun.com/contents/436/613.html"
category: "開發者手冊 / 后端API / H3.DataModel.Script / Parser"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : Parser
说明 : 表达式解析器 属性 : 

| 名称 | 说明 |
| --- | --- |
| Formula | 表达式 |
| ExecutionQueueLength | 计算逻辑单元长度 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| VariablePrefix | 做花括号 |
| VariablePostfix | 右括号 |


构造方法名称 : #ctor(H3.Organization.IOrganization,H3.DataModel.IBizObjectSchemaManager,System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "objectManager" | 业务对象管理器 |
| "formula" | 公式 |
| "errorMsg" | 错误信息 |
| 返回值 |  |
| |  |


方法名称 : Calculate(H3.DataModel.Script.IVariableTable,System.String@)

| 参数 | 说明 |
| --- | --- |
| "variables" | 传入数据 |
| "errorMsg" | 错误信息 |
| 返回值 |  |
| 计算结果 |  |


方法名称 : Describe(H3.DataModel.BizObjectSchemaSummary,System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectSchemaSummary})

| 参数 | 说明 |
| --- | --- |
| "schema" | 当前表单 |
| "schemas" | 要查找的表单集合 |
| 返回值 |  |
| 描述 |  |


方法名称 : ParseJs(H3.DataModel.BizObjectSchemaSummary,System.String,System.String@,System.String@,System.Collections.Generic.Dictionary{System.String,System.String},System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "schema" | 当前表单 |
| "dataField" | 字段 |
| "js" | 解析成的JS语句 |
| "errorMessage" | 错误信息 |
| "parameterTable" | 表达式中参数列表 |
| "isFrontEndCheck" | 是否是前台检查 |
| 返回值 |  |
| 解析是否成功 |  |


方法名称 : ParseBackScript(H3.Data.Database.DatabaseType,H3.DataModel.BizObjectSchemaSummary,System.Boolean,System.Boolean,System.String,System.String@,H3.DataModel.Script.FileScript@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "dbType" | |
| "schema" | |
| "parseFileScriptOnly" | |
| "includeInheritedAndRelation" | |
| "CurrentChangeRuleObjectId" | |
| "sql" | |
| "fileEvent" | |
| "errorMessage" | |
| 返回值 |  |
| |  |


方法名称 : ParseBackScriptForWhereCondition(H3.Data.Database.DatabaseType,H3.DataModel.BizObjectSchemaSummary,System.Boolean,System.Boolean,System.String,System.String@,H3.DataModel.Script.FileScript@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "dbType" | |
| "schema" | |
| "parseFileScriptOnly" | |
| "includeInheritedAndRelation" | |
| "CurrentChangeRuleObjectId" | |
| "sql" | |
| "fileEvent" | |
| "errorMessage" | |
| 返回值 |  |
| |  |


方法名称 : IsProcedureScript(System.String)

| 参数 | 说明 |
| --- | --- |
| "expression" | |
| 返回值 |  |
| |  |


方法名称 : IsFileScript(System.String)

| 参数 | 说明 |
| --- | --- |
| "expression" | |
| 返回值 |  |
| |  |


方法名称 : ParseReportSourceSql(H3.Data.Database.DatabaseType,System.String@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "dbType" | 数据库类型 |
| "sql" | sql语句 |
| "errorMessage" | 错误消息 |
| 返回值 |  |
| |  |


方法名称 : ParseFilter(H3.DataModel.BizObjectSchemaSummary,System.Collections.Generic.Dictionary{System.String,System.Object},H3.Data.Filter.Filter@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "schema" | |
| "values" | |
| "filter" | 解析成的Filter |
| "errorMessage" | 错误信息 |
| 返回值 |  |
| 是否成功 |  |


方法名称 : GetVariables

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Validate(System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{System.String}},System.Collections.Generic.List{System.String},System.String\[\]@,System.Collections.Generic.List{System.String})

| 参数 | 说明 |
| --- | --- |
| "VariableFormulaTable" | 带有公式的变量，格式是(变量名, 公式) |
| "AllVarialbles" | 所有变量名称 |
| "ErrorVariables" | 出现错误的变量 |
| "Errors" | 错误提示信息 |
| 返回值 |  |
| 如果验证合法，则返回true；否则返回false，并记录哪些变量是有错误的 |  |


方法名称 : GetFunctions(H3.Organization.IOrganization,H3.DataModel.IBizObjectManager,H3.DataModel.Script.FunctionScenarioType,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "objectManager" | 业务对象管理器 |
| "scenarioType" | 函数支持的场景的类型 |
| "isDevMode" | 是开发者 |
| 返回值 |  |
| |  |


方法名称 : CreateHelper(H3.Organization.IOrganization,H3.DataModel.IBizObjectSchemaManager,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "organization" | |
| "objectManager" | |
| "isDevMode" | |
| 返回值 |  |
| |  |


方法名称 : GetSqlVariableName(H3.Data.Database.DatabaseType,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "dbType" | |
| "schemaCode" | |
| "propertyName" | |
| 返回值 |  |
| |  |


方法名称 : GetDeclarationSql(H3.Data.Database.DatabaseType,H3.DataModel.BizObjectSchemaSummary,System.Boolean,System.String\[\]@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "databaseType" | |
| "schema" | |
| "isChild" | |
| "declarations" | |
| "selectInto" | |
| 返回值 |  |
| |  |


方法名称 : GetOwenerObjectAndRelationObject(System.Text.StringBuilder@,System.Text.StringBuilder@,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{System.String}},H3.Data.Database.DatabaseType,System.String,H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "ownerStringResult" | |
| "relationStringResult" | |
| "AllInheritedFunctionNode" | |
| "dbType" | |
| "CurrentChangeRuleObjectId" | |
| "currentSchema" | |
| 返回值 |  |
| |  |


方法名称 : GetCodeAndIsVariable(System.Collections.Generic.Dictionary{System.String,H3.DataModel.Script.RuleNode},H3.DataModel.Script.RuleNode)

| 参数 | 说明 |
| --- | --- |
| "allNodes" | |
| "node" | |
| 返回值 |  |
| |  |