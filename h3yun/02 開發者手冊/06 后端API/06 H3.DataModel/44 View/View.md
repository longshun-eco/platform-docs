---
title: "View"
source: "https://help.h3yun.com/contents/383/422.html"
category: "開發者手冊 / 后端API / H3.DataModel / View"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : View
说明 : 视图，业务对象通过视图来控制字段的读写权限和方法的调用权限。比如：一个采购订单对象，在新建的状态下可以修改发货日期字段，而发货状态的时候，我们禁止用户修改发货日期字段。 属性 : 

| 名称 | 说明 |
| --- | --- |
| Name | 视图名称 |
| Description | 视图描述 |
| Condition | 启用的条件 |
| PropertyStates | 该视图中包含的所有的字段状态 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| DefaultViewCode\_DraftView | 草稿视图的Key值 |
| DefaultViewCode\_EffectiveView | 生效视图 |


构造方法名称 : #ctor(System.String,H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "name" | 视图名称 |
| "schema" | 视图对应的业务对象 |
| 返回值 |  |
| |  |


方法名称 : GetPropertyState(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 字段名称 |
| 返回值 |  |
| 字段状态 |  |


方法名称 : OnPropertyAdded(H3.DataModel.PropertySchema,System.String)

| 参数 | 说明 |
| --- | --- |
| "property" | 字段 |
| "viewName" | 视图名称 |
| 返回值 |  |
| 如果字段不存在则返回true，否则返回false |  |


方法名称 : OnPropertyRemoved(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 字段名称 |
| 返回值 |  |
| 如果更新视图成功，则返回true，否则返回false |  |


方法名称 : OnPropertyRenamed(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "oldPropertyName" | 旧的字段名称 |
| "newPropertyName" | 新的字段名称 |
| 返回值 |  |
| |  |


方法名称 : Validate(H3.Organization.IOrganization,H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "schema" | 业务对象模式 |
| 返回值 |  |
| 如果合法，则返回Valid=true；否则返回Valid=false |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlDocument" | xml文档 |
| "xmlElement" | xml元素 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlElement" | xml元素 |
| 返回值 |  |