---
title: "IWorkItemManager"
source: "https://help.h3yun.com/contents/655/410.html"
category: "開發者手冊 / 后端API / H3.Workflow.WorkItem / IWorkItemManager"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : IWorkItemManager
说明 : 工作项管理器 
方法名称 : AddWorkItems(H3.Workflow.WorkItem.WorkItem\[\])

| 参数 | 说明 |
| --- | --- |
| "workItems" | 新增的工作项 |
| 返回值 |  |
| 添加的工作项的ID |  |


方法名称 : CancelWorkItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "workItemId" | 工作项ID |
| 返回值 |  |
| 执行结果 |  |


方法名称 : UpdateWorkItemSummary(H3.Workflow.WorkItem.WorkItem)

| 参数 | 说明 |
| --- | --- |
| "workItem" | 更改的工作项目 |
| 返回值 |  |
| |  |


方法名称 : GetWorkItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "workItemId" | 工作项ID |
| 返回值 |  |
| 获得的工作项 |  |


方法名称 : GetOvertimeWorkItems

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 所有的超期的未完成任务 |  |


方法名称 : GetWorkItems(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "workItemIds" | 工作项Id |
| 返回值 |  |
| 工作项 |  |


方法名称 : ForwardWorkItem(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "workItemId" | 工作项ID |
| "participant" | 接收人 |
| "comment" | 转发意见 |
| 返回值 |  |
| 执行结果 |  |


方法名称 : HandOver(System.String,System.String,System.String\[\],System.String@)

| 参数 | 说明 |
| --- | --- |
| "sourceUserId" | 任务源用户ID |
| "targetUserId" | 任务目标用户ID |
| "schemaCodes" | 业务对象模式编码，如果为Null，表示不区分schemaCode，也就是转移所有的workItem |
| "errorMsg" | 错误信息 |
| 返回值 |  |
| |  |


方法名称 : ActivateWorkItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "workItemId" | 工作项ID |
| 返回值 |  |
| 执行结果 |  |


方法名称 : DoWorkItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "workItemId" | 工作项ID |
| 返回值 |  |
| 执行结果 |  |


方法名称 : FinishWorkItem(System.String,System.String,H3.Workflow.WorkItem.AccessMethod,H3.Data.BoolValue,System.String,System.String,H3.Workflow.WorkItem.ActionEventType)

| 参数 | 说明 |
| --- | --- |
| "userId" | 提交人员 |
| "workItemId" | 工作项ID |
| "finishAccessMethod" | 提交人员的接入方式 |
| "approval" | 审批结果 |
| "comment" | 审批意见 |
| "actionName" | 操作名称 |
| "actionEventType" | 操作的事件的类型:H3.Workflow.WorkItem.ActionEventType |
| 返回值 |  |
| 执行结果 |  |