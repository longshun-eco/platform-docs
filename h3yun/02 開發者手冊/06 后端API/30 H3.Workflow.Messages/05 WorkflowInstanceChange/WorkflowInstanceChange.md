---
title: "WorkflowInstanceChange"
source: "https://help.h3yun.com/contents/742/590.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / WorkflowInstanceChange"
updated: 2025-12-16
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkflowInstanceChange
说明 : 流程实例的变更信息 属性 : 

| 名称 | 说明 |
| --- | --- |
| AppCode | 应用的编码 |
| SchemaCode | 业务对象模式编码 |
| BizObjectId | 业务对象Id |
| WorkflowVersion | 流程模板版本号 |
| InstanceId | 流程模板版本号 |
| OldState | 变更前的状态 |
| NewState | 变更后的状态 |
| ClientActivities | 人参与的活动的状态 |



构造方法名称 : #ctor(System.String,System.String,System.Int32,System.String,System.String,H3.Workflow.Instance.WorkflowInstanceState,H3.Workflow.Instance.WorkflowInstanceState)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用的编码 |
| "schemaCode" | 业务对象模式编码 |
| "workflowVersion" | 流程模板版本号 |
| "bizObjectId" | 业务对象Id |
| "instanceId" | 流程实例Id |
| "oldState" | 流程的旧状态 |
| "newState" | 流程的新状态 |
| 返回值 |  |
| |
 |