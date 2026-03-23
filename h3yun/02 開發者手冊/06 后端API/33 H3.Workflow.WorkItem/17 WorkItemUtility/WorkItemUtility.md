---
title: "WorkItemUtility"
source: "https://help.h3yun.com/contents/662/436.html"
category: "開發者手冊 / 后端API / H3.Workflow.WorkItem / WorkItemUtility"
updated: 2025-12-14
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkItemUtility

说明 : 工作项类型的帮助 
方法名称 : GetNotCircularTypes

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 工作项类型 |  |


方法名称 : IsParticipativeType(H3.Workflow.WorkItem.WorkItemType)

| 参数 | 说明 |
| --- | --- |
| "type" | 工作项类型 |
| 返回值 |  |
| 如果工作项类型是审批、读、填写类型的时候，返回true，如果是征询意见、传阅、协办，则返回false |  |


方法名称 : IsUnfinished(H3.Workflow.WorkItem.WorkItemState)

| 参数 | 说明 |
| --- | --- |
| "state" | |
| 返回值 |  |
| |  |


方法名称 : GetUnfinishedStates

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |