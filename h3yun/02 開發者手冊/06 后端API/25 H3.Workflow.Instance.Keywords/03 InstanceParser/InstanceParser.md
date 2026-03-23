---
title: "InstanceParser"
source: "https://help.h3yun.com/contents/700/792.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance.Keywords / InstanceParser"
updated: 2025-12-19
tags:
  - h3yun
  - 開發者手冊
---
类名 : InstanceParser
说明 : 流程实例解析器 
成员 : 

| 名称 | 说明 |
| --- | --- |
| InstanceName | 流程名称 |
| InstanceId | 流程ID |
| OriginateDate | 发起日期 |
| OriginateTime | 发起时间 |
| CurrentTime | 当前时间 |
| OriginateFullTime | 发起的时间的全值 |
| AllParticipants | 该流程现有的所有参与者 |
| ActivityCode | 当前活动的编码 |


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
| "workItemManager" | 流程任务管理器 |
| "query" | 查询管理器 |
| 返回值 |  |
| |  |


方法名称 : GetDisplayName(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键字 |
| 返回值 |  |
| 显示名称 |  |


方法名称 : GetBizDataType(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键字 |
| 返回值 |  |
| 数据类型 |  |


方法名称 : IsParticipant(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键则 |
| 返回值 |  |
| bool 是否参与者字段 |  |


方法名称 : IsKeyword(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键字 |
| 返回值 |  |
| bool 是否关键字 |  |


方法名称 : GetKeywords

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 数组 关键字集合 |  |


方法名称 : ParseValue(System.String,H3.Workflow.Instance.WorkflowInstance,System.String,System.Int32,System.Int32,System.String,System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit})

| 参数 | 说明 |
| --- | --- |
| "itemName" | 项名称 |
| "context" | 流程实例 |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程模板版本号 |
| "tokenId" | 令牌Id，或者叫步骤Id，流程实例每走过一个活动该ID会自动加1。令牌与活动是N:1的关系 |
| "filler" | 当前用户，构造该函数的用户，用于获得当前用户的信息 |
| "orgCache" | 用于缓存已经访问过的组织结构对象 |
| 返回值 |  |
| 实例返回值 |  |


方法名称 : CreateTree(H3.Workflow.Instance.Keywords.KeyWordNode)

| 参数 | 说明 |
| --- | --- |
| "parentNode" | 父节点 |
| 返回值 |  |
| |
 |