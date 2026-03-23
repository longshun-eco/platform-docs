---
title: "BizObjectSchemaSummary"
source: "https://help.h3yun.com/contents/352/358.html"
category: "開發者手冊 / 后端API / H3.DataModel / BizObjectSchemaSummary"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizObjectSchemaSummary
说明 : 业务对象的模式的摘要，这个类只是业务对象模式的主要信息，所以体量会小很多，获取这个对的速度会快很多，用户体验也会更好 属性 : 

| 名称 | 说明 |
| --- | --- |
| SchemaCode | 唯一编码 |
| TableName | 表名 |
| UsageType | 获取或设置数据模型的应用方式 |
| DisplayName | 显示名称 |
| FullName | 业务对象模式的全名称，该名称由显示名称和编码组合而成，所以，该名称是可以变化的，不能作为唯一确定业务对象模式的键值 |
| ParentSchema | 如果本模式是其他模式的子模式，那么在这里指定对应的父模式 |
| ParentPropertyName | 如果本模式是其他模式的子模式，那么在这里指定对应的父模式中自己所对应的属性名称 |
| RecursiveSchemaCodes | 递归获得子模式编码 |
| ChildSchemas | 本模式拥有的全部递归子模式，即子模式和子模式的ChildSchemas |
| Properties | 所有直接的属性 |
| PropertiesExcludeRemoved | 排除已经标注为删除的属性 |
| NameSchema | 摘要信息，比如：{OwnerId}发表了文章{Title} |
| SummarySchema | 摘要信息，比如：{OwnerId}发表了文章{Title} |



构造方法名称 : #ctor(H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "schema" | |
| 返回值 |  |
| |  |


方法名称 : GetRootSchema

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetRootSchema(System.String\[\]@)

| 参数 | 说明 |
| --- | --- |
| "properties" | 如何从根模式中找到自己 |
| 返回值 |  |
| 根模式，如果自己就是根模式的话，则返回自己 |  |


方法名称 : GetChildSchema(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 子模式的编码 |
| 返回值 |  |
| 子模式 |  |


方法名称 : GetProperty(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| 属性模式 |  |


方法名称 : GetPropertyNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 属性名称 |  |


方法名称 : GetBizDataType(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 字段名称 |
| 返回值 |  |
| 字段类型 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | 索引键 |
| 返回值 |  |
| 返回 键值 |  |