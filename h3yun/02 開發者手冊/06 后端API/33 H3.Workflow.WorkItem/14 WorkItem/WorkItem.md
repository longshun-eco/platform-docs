---
title: "WorkItem"
source: "https://help.h3yun.com/contents/659/429.html"
category: "開發者手冊 / 后端API / H3.Workflow.WorkItem / WorkItem"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkItem
说明 : 工作项，每个流程活动只能给每个用户发送至多一个工作项。工作项可以进行转发、委托、征询意见、打回等操作 属性 : 

| 名称 | 说明 |
| --- | --- |
| WorkItemId | 获取或设置工作任务ID，等同于 ObjectID |
| Participant | 获取或设置任务参与者 |
| OriginatorParent | 参与者所属OU |
| Finisher | 实际的完成者，比如代办或者委托之类的，这个属性起作用 |
| FinishAccessMethod | 完成接入方式 |
| WorkflowVersion | 对应的工作流模板的属性 |
| InstanceId | 对应的流程的ID |
| AppCode | AppID |
| SchemaCode | 业务对象模式编码 |
| BizObjectId | 业务对象ID |
| TokenId | 对应流程中的令牌的ID |
| ActivityCode | 对应的活动的编码 |
| ActivityDisplayName | 对应的活动的显示名称 |
| DisplayName | 显示名称，显示名称可以是一个包含流程数据项的组合字符串，这样一来，显示名称可以展现在待办任务列表上，用户可以通过待办任务列表，直接看到这个工作项是包含什么内容的 |
| ItemSummary | 摘要，摘要可以是一个包含流程数据项的组合字符串，这样一来，摘要可以展现在任务列表的提示栏中，用户可以通过提示栏，直接看到这个工作项是包含什么内容的，摘要也可以用于邮件通知 |
| State | 状态 |
| IsFinished | 是否是已经完成的状态 |
| IsUnfinished | 是否是未完成的状态 |
| ReceiveTime | 这个值由作业管理器来设置，而不是创建的时候设置 |
| StartTime | 开始这个任务的时间 |
| WaitTime | 等待时间的Ticks |
| FinishTime | 完成时间 |
| UsedTime | 使用时间的Ticks |
| StayTimeSpan | 停留时间。如果是完成的工作项，那么停留时间=完成时间-接收时间；否则停留时间=当前时间-接收时间。 |
| AllowedTime | 许可完成时间 |
| Delegant | 代理给他人的源，比如：A委托给B，那么B将会是这个工作项的参与者，A是Delegant；同样，对于转发也是这样的，A转发给B，B是参与者，A是Delegant |
| Urged | 是否被催办过 |
| ItemType | 工作列的的类型 |
| IsParticipative | 是否参与流程类的工作项 |
| Originator | 流程实例的发起人 |
| Approval | 对该工作项是否同意 |
| ItemComment | 对于该工作项的意见 |
| Receiptor | 转交工作的时候的接收人 |
| ActionName | 操作名称 |
| PreActionEventType | 上一个步骤操作的事件的类型 |
| ActionEventType | 操作的事件的类型 |
| Notify | 是否通知用户，这个字段是系统内部使用，并不存储在数据库中 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名 |
| NullWorkItemId | 空工作项ID |
| PropertyName\_Participant | 属性名称 |
| PropertyName\_OriginatorParent | 属性名称 |
| PropertyName\_Finisher | 属性名称 |
| PropertyName\_FinishAccessMethod | 属性名称 |
| PropertyName\_WorkflowVersion | 属性名称 |
| PropertyName\_InstanceId | 属性名称 |
| PropertyName\_AppCode | 属性名称 |
| PropertyName\_SchemaCode | 属性名称 |
| PropertyName\_BizObjectId | 属性名称 |
| PropertyName\_TokenId | 属性名称 |
| PropertyName\_ActivityCode | 属性名称 |
| PropertyName\_ActivityDisplayName | 属性名称 |
| PropertyName\_DisplayName | 属性名称 |
| PropertyName\_ItemSummary | 属性名称 |
| PropertyName\_State | 属性名称 |
| PropertyName\_ReceiveTime | 属性名称 |
| PropertyName\_StartTime | 属性名称 |
| PropertyName\_WaitTime | 属性名称 |
| PropertyName\_FinishTime | 属性名称 |
| PropertyName\_UsedTime | 属性名称 |
| PropertyName\_AllowedTime | 属性名称 |
| PropertyName\_Delegant | 属性名称 |
| PropertyName\_Urged | 属性名称 |
| PropertyName\_ItemType | 属性名称 |
| PropertyName\_Originator | 属性名称 |
| PropertyName\_Approval | 属性名称 |
| PropertyName\_ItemComment | 属性名称 |
| PropertyName\_Receiptor | 属性名称 |
| PropertyName\_ActionName | 属性名称 |
| PropertyName\_PreActionEventType | 属性名称 |
| PropertyName\_ActionEventType | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.String,System.String,System.Int32,System.String,System.String,System.String,System.String,System.Int32,System.String,System.String,System.String,H3.Workflow.WorkItem.WorkItemType,H3.Workflow.Template.PermittedActions,System.String,System.DateTime,H3.Workflow.WorkItem.ActionEventType)

| 参数 | 说明 |
| --- | --- |
| "participant" | 参与者ID，也就是工作项的处理人 |
| "participantParent" | 参与者所属的机构，可以是OU或者公司 |
| "appCode" | 应用编码 |
| "workflowVersion" | 流程模板版本号 |
| "schemaCode" | 业务对象模式编码 |
| "bizObjectId" | 业务对象ID |
| "instanceId" | 流程实例的ID |
| "activityCode" | 流程活动的编码 |
| "activityDisplayName" | 流程活动的名称，该活动名称在流程设计器中定义 |
| "tokenId" | 令牌ID，或者叫步骤ID，流程实例每走过一个活动该ID会自动加1。令牌与活动是N:1的关系 |
| "displayName" | 显示名称 |
| "summary" | 摘要 |
| "delegant" | 代理给他人的源，比如：A委托给B，那么B将会是这个工作项的参与者，A是Delegant；同样，对于转发也是这样的，A转发给B，B是参与者，A是Delegant |
| "itemType" | 工作项的类型，比如：征询意见、协办等 |
| "permittedActions" | 允许的操作 |
| "originator" | 流程实例的发起人，这里指的发起人的ID |
| "allowedTime" | 计划使用时间，通过该属性可以计算出这个工作项的计划完成时间 |
| "preActionEventType" | 上一活动节点操作方式 |
| 返回值 |  |
| |  |


方法名称 : ToString

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Clone

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |
 |