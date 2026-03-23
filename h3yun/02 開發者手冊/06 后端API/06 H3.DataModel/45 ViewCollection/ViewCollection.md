---
title: "ViewCollection"
source: "https://help.h3yun.com/contents/384/424.html"
category: "開發者手冊 / 后端API / H3.DataModel / ViewCollection"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : ViewCollection
说明 : 业务对象视图集合，该类保存了业务对象模式中的所有视图 属性 : 

| 名称 | 说明 |
| --- | --- |
| Schema | 业务对象模型 |
| Item(System.String) | 根据视图名称获得视图 |
| Count | 视图的数量 |
| Item(System.Int32) | 根据视图的索引获得视图 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Add(System.String)

| 参数 | 说明 |
| --- | --- |
| "name" | 视图名称 |
| 返回值 |  |
| 如果添加成功，则返回true；否则返回false |  |


方法名称 : Update(H3.DataModel.View)

| 参数 | 说明 |
| --- | --- |
| "view" | 视图 |
| 返回值 |  |
| |  |


方法名称 : Remove(System.String)

| 参数 | 说明 |
| --- | --- |
| "name" | 视图名称 |
| 返回值 |  |
| |  |


方法名称 : OnPropertyAdded(H3.DataModel.PropertySchema,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "property" | 字段名称 |
| "pathes" | |
| 返回值 |  |
| |  |


方法名称 : OnPropertyRemoved(System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 字段名称 |
| "pathes" | |
| 返回值 |  |
| |  |


方法名称 : OnPropertyRenamed(System.String,System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "oldPropertyName" | 旧的字段名称 |
| "newPropertyName" | 新的字段名称 |
| "pathes" | |
| 返回值 |  |
| |  |


方法名称 : Validate(H3.Organization.IOrganization,H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "schema" | 业务对象模式 |
| 返回值 |  |
| 如果合法，则返回Valid=true；否则返回Valid=false |  |


方法名称 : GetView(H3.DataModel.BizObject)

| 参数 | 说明 |
| --- | --- |
| "obj" | 业务对象 |
| 返回值 |  |
| 业务对象当前状态对应的视图 |  |