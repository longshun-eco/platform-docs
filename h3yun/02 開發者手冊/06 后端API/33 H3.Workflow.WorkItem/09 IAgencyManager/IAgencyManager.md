---
title: "IAgencyManager"
source: "https://help.h3yun.com/contents/654/409.html"
category: "開發者手冊 / 后端API / H3.Workflow.WorkItem / IAgencyManager"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : IAgencyManager
说明 : 委托关系管理器。当系统向用户A发送一个工作项的时候，会首先检查委托设置，如果存在委托，则发给委托人 
方法名称 : Add(H3.Workflow.WorkItem.Agency)

| 参数 | 说明 |
| --- | --- |
| "agency" | 委托关系对象 |
| 返回值 |  |
| 返回操作是否成功 |  |


方法名称 : Update(H3.Workflow.WorkItem.Agency)

| 参数 | 说明 |
| --- | --- |
| "agency" | 委托关系对象 |
| 返回值 |  |
| 返回操作是否成功 |  |


方法名称 : GetUserAgencies(System.String)

| 参数 | 说明 |
| --- | --- |
| "userId" | 委托人ID |
| 返回值 |  |
| 所有已经生效的委托关系 |  |


方法名称 : GetAgent(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "userId" | 委托人ID |
| "schemaCode" | 流程模板编码 |
| "originator" | 流程的发起人 |
| 返回值 |  |
| 如果没有找到最终代理人，则返回为Null |  |


方法名称 : Remove(System.String)

| 参数 | 说明 |
| --- | --- |
| "agencyId" | 委托关系ID |
| 返回值 |  |
| |  |


方法名称 : RemoveWorkflow(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| |  |


方法名称 : GetAgency(System.String)

| 参数 | 说明 |
| --- | --- |
| "agencyId" | 委托关系ID |
| 返回值 |  |
| 委托关系 |  |


方法名称 : Exists(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "userId" | 委托人ID |
| "schemaCode" | 流程模板编码 |
| "originator" | 流程发起人 |
| 返回值 |  |
| 是否存在关系定义 |  |


方法名称 : CheckWorkItemAgency(System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "userId" | 委托人ID |
| "agentId" | 受托人ID |
| "schemaCode" | 流程模板编码 |
| "originator" | 发起人 |
| 返回值 |  |
| 是否存在委托关系 |  |


方法名称 : CheckOriginateAgency(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "userId" | 委托人ID |
| "agentId" | 受托人ID |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| 是否存在委托关系 |  |


方法名称 : GetOriginateAgencyTable(System.String,System.String,System.Data.DataTable,System.String)

| 参数 | 说明 |
| --- | --- |
| "userId" | 委托人 |
| "agentId" | 被委托人 |
| "workflowTable" | 所有委托人可以发起的流程 |
| "columnCode" | WorkflowTable的SchemaCode列的列名称 |
| 返回值 |  |
| 被委托人可以帮助委托人发起的所有流程模板的表 |  |


方法名称 : GetOriginateOriginators(System.String)

| 参数 | 说明 |
| --- | --- |
| "agentId" | 被委托人，禁止为空 |
| 返回值 |  |
| 委托关系 |  |