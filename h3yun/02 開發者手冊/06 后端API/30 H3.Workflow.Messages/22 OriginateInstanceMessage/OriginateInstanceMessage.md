---
title: "OriginateInstanceMessage"
source: "https://help.h3yun.com/contents/759/664.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / OriginateInstanceMessage"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : OriginateInstanceMessage
说明 : 发起一个流程实例，包括创建和启动他 属性 : 

| 名称 | 说明 |
| --- | --- |
| BizObjectId | 业务对象ID |
| SchemaCode | 流程模板的类型 |
| WorkflowVersion | 工作流模板的版本 |
| Originator | 发起人 |
| IsChildInstance | 是否是子流程 |
| ParentInstanceId | 父流程实例ID |
| ParentActivityName | 父流程实例的活动名称 |
| NotifyParentActivityFinished | 如果是子流程，在结束的时候，是否自动通知父流程 |
| ParentActivityTokenId | 如果是子流程并且在结束的时候要通知父流程，那么该字段用于记录该子流程对应到父流程的Token |
| FinishStartActivity | 是否要自动结束开始节点 |
| ActivateDestActivity | 如果要自动结束开始节点，默认情况下，流程会自动往下走。如果不希望流程按照流程设计器上设定的路由走，那么该字段用于跳转到其他路由活动上。 |
| DestActivityParticipants | 如果要跳转到其他路由活动上，该字段记录目标路由活动的参与者 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.Int32,System.String,System.String,System.Boolean,System.String,System.String,System.Boolean,System.Int32,System.Boolean,System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "bizObjectId" | 业务实例数据ID |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程模板版本号 |
| "instanceId" | 流程实例ID |
| "originator" | 流程实例的发起人，这里指的发起人的ID |
| "isChildInstance" | 是否是子流程 |
| "parentInstanceId" | 父流程实例ID |
| "parentActivityName" | 父流程实例的活动名称 |
| "notifyParentActivityFinished" | 如果是子流程，在结束的时候，是否自动通知父流程 |
| "parentActivityTokenId" | 如果是子流程并且在结束的时候要通知父流程，那么该字段用于记录该子流程对应到父流程的Token |
| "finishStartActivity" | 是否要自动结束开始节点 |
| "activateDestActivity" | 如果要自动结束开始节点，默认情况下，流程会自动往下走。如果不希望流程按照流程设计器上设定的路由走，那么该字段用于跳转到其他路由活动上 |
| "destActivityParticipants" | 如果要跳转到其他路由活动上，该字段记录目标路由活动的参与者 |
| 返回值 |  |
| |
 |