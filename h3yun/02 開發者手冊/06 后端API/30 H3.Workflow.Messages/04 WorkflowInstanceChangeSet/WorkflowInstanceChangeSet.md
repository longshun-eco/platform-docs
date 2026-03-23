---
title: "WorkflowInstanceChangeSet"
source: "https://help.h3yun.com/contents/741/587.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / WorkflowInstanceChangeSet"
updated: 2025-12-18
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkflowInstanceChangeSet
说明 : 流程在处理完消息后会变更一些流程实例，在这里记录处理某个消息发生变更的所有流程实例，由于处理一个消息可能会影响多个流程实例（子流程），所以这里是一个集合 属性 : 

| 名称 | 说明 |
| --- | --- |
| Instances | 变更流程实例集合 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetInstance(System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | |
| 返回值 |  |
| |  |


方法名称 : GetWorkItemId(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | |
| "activityCode" | |
| "participantId" | |
| 返回值 |  |
| |  |


方法名称 : AddWorkItem(H3.Workflow.WorkItem.WorkItem,System.String)

| 参数 | 说明 |
| --- | --- |
| "item" | |
| "participantName" | |
| 返回值 |  |
| |  |


方法名称 : Peek(System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | |
| 返回值 |  |
| |
 |