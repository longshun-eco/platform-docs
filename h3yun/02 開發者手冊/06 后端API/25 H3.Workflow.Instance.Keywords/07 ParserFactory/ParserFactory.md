---
title: "ParserFactory"
source: "https://help.h3yun.com/contents/704/798.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance.Keywords / ParserFactory"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : ParserFactory
说明 : 数据关键字 属性 : 

| 名称 | 说明 |
| --- | --- |
| Parsers | 解析器集合 |



构造方法名称 : #ctor(H3.IEngine)

| 参数 | 说明 |
| --- | --- |
| "engine" | 流程引擎 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Workflow.Instance.IWorkflowInstanceManager,H3.Workflow.Template.IWorkflowTemplateManager,H3.Organization.IOrganization,H3.Workflow.WorkItem.IWorkItemManager,H3.Query)

| 参数 | 说明 |
| --- | --- |
| "workflowInstanceManager" | 流程实例管理器 |
| "workflowManager" | 流程管理器 |
| "organization" | 组织机构管理器 |
| "workItemManager" | 任务管理器 |
| "query" | 查询管理器 |
| 返回值 |  |
| |  |


方法名称 : GetDisplayName(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键字 |
| 返回值 |  |
| 显示名称 |  |


方法名称 : GetKeywordType(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键字 |
| 返回值 |  |
| 关键字的类型 |  |


方法名称 : GetKeywordBizDataType(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键字 |
| 返回值 |  |
| 关键字的逻辑类型 |  |


方法名称 : IsKeyParticipant(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 字符串 |
| 返回值 |  |
| 如果是参与者类型的关键字，则返回true，否则返回false |  |


方法名称 : IsKeyword(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 字符串 |
| 返回值 |  |
| 如果是关键字，则返回true，否则返回false |  |


方法名称 : GetFormSystemData

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| string\[\] |  |


方法名称 : GetKeywords

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 所有的关键字 |  |


方法名称 : GetDataTreeNode

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 关键字树型结构 |  |


方法名称 : ParseValue(System.String,H3.Workflow.Instance.WorkflowInstance,System.String,System.Int32,System.Int32,System.String,System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit})

| 参数 | 说明 |
| --- | --- |
| "itemName" | 项名称 |
| "workflowInstance" | 流程实例的上下文 |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程模板版本号 |
| "tokenId" | 令牌ID |
| "filler" | 当前用户 |
| "orgCache" | 用于缓存已经访问过的组织结构对象 |
| 返回值 |  |
| 解析出来的值 |  |