---
title: "WorkflowInstance"
source: "https://help.h3yun.com/contents/686/743.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance / WorkflowInstance"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkflowInstance
说明 : 流程实例的上下文 属性 : 

| 名称 | 说明 |
| --- | --- |
| WorkflowDisplayName | 流程名称 |
| InstanceId | 流程实例ID |
| InstanceName | 流程实例的名称，该名称可以来自于流程模板中定义的名称，也可以使用户指定的 |
| Originator | 发起人 |
| OriginatorParent | 发起人发起该流程的时候所属的组织 |
| IsChildInstance | 是否是其他实例的子流程 |
| ParentInstanceId | 父实例的ID |
| ParentActivityCode | 创建该子流程的父流程活动的名称 |
| NotifyParentFinished | 当完成的时候是否通知他的父实例已完成 |
| ParentActivityTokenId | 创建该子流程的父流程的活动的TokenId |
| WorkflowVersion | 工作流模板的版本 |
| AppCode | 应用的编码 |
| SchemaCode | 业务对象模式编码 |
| BizObjectId | 业务对象ID |
| State | 状态 |
| IsUnfinished | 当前流程实例是否处于未完成状态 |
| IsFinished | 当前流程实例是否处于完成状态 |
| IsCanceled | 当前流程实例是否已经被取消 |
| InitiativeTokenId | 初始的TokenId，如果当前状态为Starting，那么该值有效 |
| FinalTokenId | 这个令牌是流程活动的最后一个令牌的ID，如果当前状态为Finishing，那么该值有效 |
| NextTokenId | 下一个新的Token的ID，初始值必须为InitialTokenId，因为有ClientAction需要用他来判断是否是第一个，以决定是否发送邮件。 |
| Tokens | 活动上下文数组。只有已经触发过的活动才会数组中有记录。 |
| RunningActivties | 当前运行状态的活动 |
| CreatedTime | 创建日期 |
| StayTime | 滞留时间，如果流程未完成，则是当前时间减去创建时间；否则是完成时间减去创建时间。 |
| StartTime | 启动时间 |
| FinishTime | 完成时间 |
| UsedTime | 使用时间，只有流程完成的时候才计算这个时间，这个时间为完成时间减去创建时间。 |
| PlanFinishTime | 计划完成时间，按照发起人的工作日历来计算 |
| UsedTimeRate | 流程实例的完成时间 |
| Approval | 是否最终审批通过，如果通过则设置为1，如果没有进行审批则为-1，否则设置为0 |
| Remind | 流程结束后通知给发起人，发起人是否查看到该状态 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| UnspecifiedId | 未指定的ID |
| PropertyName\_WorkflowDisplayName | 流程名称 |
| PropertyName\_InstanceId | 属性名称 |
| PropertyName\_InstanceName | 属性名称 |
| PropertyName\_Originator | 属性名称 |
| PropertyName\_OriginatorParent | 属性名称 |
| PropertyName\_ParentInstanceId | 属性名称 |
| PropertyName\_ParentActivityName | 属性名称 |
| PropertyName\_NotifyParentFinished | 属性名称 |
| PropertyName\_ParentActivityTokenId | 属性名称 |
| PropertyName\_WorkflowVersion | 属性名称 |
| PropertyName\_AppId | 属性名称 |
| PropertyName\_SchemaCode | 流程模板编码 |
| PropertyName\_BizObjectId | 属性名称 |
| PropertyName\_State | 属性名称 |
| PropertyName\_FinalTokenId | 属性名称 |
| PropertyName\_NextTokenId | 属性名称 |
| PropertyName\_Tokens | 属性名称 |
| PropertyName\_CreatedTime | 属性名称 |
| PropertyName\_StartTime | 属性名称 |
| PropertyName\_FinishTime | 属性名称 |
| PropertyName\_UsedTime | 属性名称 |
| PropertyName\_PlanFinishTime | 属性名称 |
| PropertyName\_UsedTimeRate | 属性名称 |
| PropertyName\_Approval | 属性名称 |
| PropertyName\_Remind | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.String,System.String,System.String,H3.Workflow.Template.WorkflowTemplate,System.Boolean,System.String,System.String,System.Int32,System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用编码 |
| "schemaCode" | 数据模型编码 |
| "bizObjectId" | 数据模型ID |
| "originator" | 发起人 |
| "originatorParent" | 以哪个部门的身份发起的 |
| "workflow" | 流程模板 |
| "isChildInstance" | 是否是子流程 |
| "parentInstanceId" | 如果是子流程，该参数有效，用于记录父流程实例的ID |
| "parentActivityCode" | 如果是子流程，该参数有效，用于记录父流程实例的活动的编码 |
| "parentActivityTokenId" | 如果是子流程，该参数有效，用于记录父流程实例的活动的令牌 |
| "workflowDisplayName" | 流程名称 |
| 返回值 |  |
| |  |


方法名称 : CreateToken

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 返回一个新的令牌ID |  |


方法名称 : GetToken(System.Int32)

| 参数 | 说明 |
| --- | --- |
| "tokenId" | 活动名称 |
| 返回值 |  |
| 活动的上下文 |  |


方法名称 : GetTokens(System.String,H3.Workflow.Instance.TokenState)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 获得的编码 |
| "tokenState" | 令牌的状态 |
| 返回值 |  |
| 令牌 |  |


方法名称 : GetLastToken

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 令牌 |  |


方法名称 : GetLastToken(System.String)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 活动编码 |
| 返回值 |  |
| 令牌 |  |


方法名称 : GetPostTokens(System.Int32,H3.Workflow.Instance.TokenState)

| 参数 | 说明 |
| --- | --- |
| "tokenId" | 令牌的Id |
| "state" | 令牌的状态 |
| 返回值 |  |
| 后续令牌的Id |  |


方法名称 : GetPostTokens(System.Int32)

| 参数 | 说明 |
| --- | --- |
| "tokenId" | 令牌的Id |
| 返回值 |  |
| 后续令牌的Id |  |


方法名称 : GetPreTokens(System.Int32)

| 参数 | 说明 |
| --- | --- |
| "tokenId" | 令牌的Id |
| 返回值 |  |
| 令牌的前置令牌 |  |


方法名称 : GetTokenTable

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 流程的执行令牌记录 |  |


方法名称 : AddToken(H3.Workflow.Instance.Token)

| 参数 | 说明 |
| --- | --- |
| "token" | 执行令牌 |
| 返回值 |  |
| |  |


方法名称 : IsActivityRunning(System.String)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 活动编码 |
| 返回值 |  |
| 如果当前活动处于运行状态，则返回true，否则返回false |  |


方法名称 : GetRunningToken(System.String)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 活动编码 |
| 返回值 |  |
| 这个活动处于活动状态的令牌 |  |