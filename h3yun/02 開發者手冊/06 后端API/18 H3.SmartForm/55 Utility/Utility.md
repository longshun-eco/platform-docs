---
title: "Utility"
source: "https://help.h3yun.com/contents/615/802.html"
category: "開發者手冊 / 后端API / H3.SmartForm / Utility"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : Utility
说明 : 通用类 
方法名称 : GetNodeUrl(H3.App.FunctionNode)

| 参数 | 说明 |
| --- | --- |
| "functionNode" | |
| 返回值 |  |
| |  |


方法名称 : GetWorkItemUrl(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| "workItemId" | |
| 返回值 |  |
| |  |


方法名称 : GetFormUrl(System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "SchemaCode" | |
| "BizObjectID" | |
| "InstanceId" | |
| "WorkItemID" | |
| "Mode" | |
| 返回值 |  |
| |  |


方法名称 : GetUserInfoUrl(System.String)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetParamFormat(System.String)

| 参数 | 说明 |
| --- | --- |
| "field" | |
| 返回值 |  |
| |  |


方法名称 : GetReadAttachmentUrl(System.String)

| 参数 | 说明 |
| --- | --- |
| "fileId" | |
| 返回值 |  |
| |  |


方法名称 : GetGlobalString(System.String,System.Object)

| 参数 | 说明 |
| --- | --- |
| "language" | 语言设置 |
| "textObj" | |
| 返回值 |  |
| |  |


方法名称 : ConvertDataToWebData(H3.DataModel.BizObject,H3.SmartForm.FormSetting)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : ImportChildValues(System.Collections.Generic.Dictionary{System.String,System.Object},H3.Data.Serialization.VirtualObject\[\],H3.DataModel.BizObjectSchema,System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader},System.Collections.Generic.Dictionary{System.String,System.String},System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "values" | |
| "childbos" | |
| "childSchema" | |
| "headerTable" | |
| "unitNameTable" | |
| "onlyObjectIdAndName" | |
| 返回值 |  |
| |  |


方法名称 : ImportChildValuesTable(H3.DataModel.BizObjectSchema,System.String,System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader},System.Collections.Generic.Dictionary{System.String,System.String},System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.Dictionary{System.String,System.Object}},System.Data.DataTable)

| 参数 | 说明 |
| --- | --- |
| "parentSchema" | |
| "childSchemaCode" | |
| "headerTable" | |
| "unitNameTable" | |
| "result" | |
| "dt" | |
| 返回值 |  |
| |  |


方法名称 : GetListDataIncludeChildSchema(System.Data.DataRow,H3.DataModel.BizObjectSchema,H3.DataModel.BizObjectSchema,System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader},System.Collections.Generic.Dictionary{System.String,System.String})

| 参数 | 说明 |
| --- | --- |
| "row" | DataRow |
| "parentSchema" | 父业务模式 |
| "childSchema" | 子业务模式 |
| "headerTable" | 头信息 |
| "unitNameTable" | 用户信息 |
| 返回值 |  |
| |  |


方法名称 : GetProperty(System.String,H3.DataModel.BizObjectSchema,H3.DataModel.PropertySchema@)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名 |
| "schema" | 业务对象模式 |
| "property" | 属性 |
| 返回值 |  |
| |  |


方法名称 : GetProperty(System.String,H3.DataModel.BizObjectSchema,H3.DataModel.PropertySchema@,H3.DataModel.BizObjectSchema@)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名 |
| "schema" | 业务对象模式 |
| "property" | 属性 |
| "outSchema" | |
| 返回值 |  |
| |  |


方法名称 : GetProperty(System.String,H3.DataModel.BizObjectSchemaSummary,H3.DataModel.PropertySchemaSummary@)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名 |
| "schema" | 业务对象模式 |
| "property" | 属性 |
| 返回值 |  |
| |  |


方法名称 : GetAddressName(System.String,System.Collections.Generic.Dictionary{System.String,System.String})

| 参数 | 说明 |
| --- | --- |
| "v" | |
| "addressSourceData" | |
| 返回值 |  |
| |  |


方法名称 : GetProvinceAndOtherCode(System.String,System.String@,System.String@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "adcode" | 地址编码 |
| "province" | 省份编码 |
| "city" | 市编码 |
| "town" | 镇编码 |
| 返回值 |  |
| |  |


方法名称 : LoadFormDefaultActions

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 菜单按钮 |  |


方法名称 : LoadListViewDefaultActions

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 列表按钮 |  |