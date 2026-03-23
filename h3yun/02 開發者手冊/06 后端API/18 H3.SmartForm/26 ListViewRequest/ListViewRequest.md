---
title: "ListViewRequest"
source: "https://help.h3yun.com/contents/586/605.html"
category: "開發者手冊 / 后端API / H3.SmartForm / ListViewRequest"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : ListViewRequest
说明 : 列表请求类 属性 : 

| 名称 | 说明 |
| --- | --- |
| HasAssociation | 是否存在关联字段 |
| Associationproperty | 关联字段 |
| ChildSchemaCode | 子表查询编码 |
| Filter | 过滤条件 |
| ListScene | 列表场景 |
| SearchParams | 搜索参数 |
| DisplayName | 显示名称 |
| SchemaCode | 查询编码 |
| ListViewSetting | Query对象 |
| IsDataAclScopeTypeAll | 是否全部数据权限 |
| OrgScopeType | 组织机构范围类型 |
| Schema | 数据模型对象 |
| CurrentUserId | 当前用户ID |
| CurrentUserCode | 当前用户编码 |
| AppCode | 应用编码 |
| IsCustom | 是否自定义 |
| ModifiedTime | 修改时间 |
| IsWorkflow | 是否流程 |
| isDesignMode | 是否设计模式 |



构造方法名称 : #ctor(H3.IEngine,H3.Web.UserContext,System.Collections.Generic.Dictionary{System.String,System.String},System.String,H3.Acl.DataAclScopeType)

| 参数 | 说明 |
| --- | --- |
| "engine" | 引擎对象 |
| "userContext" | 当前上下文 |
| "valueTable" | 值对象集合 |
| "schemaCode" | 业务对象编码 |
| "orgScopeType" | 组织结构范围类型 |
| 返回值 |  |
| |  |


方法名称 : Init

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | |
| 返回值 |  |
| |
 |