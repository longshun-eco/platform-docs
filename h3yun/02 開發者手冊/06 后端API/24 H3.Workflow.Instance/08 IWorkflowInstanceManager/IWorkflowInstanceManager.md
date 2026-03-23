---
title: "IWorkflowInstanceManager"
source: "https://help.h3yun.com/contents/690/759.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance / IWorkflowInstanceManager"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : IWorkflowInstanceManager
说明 : 流程实例管理器 
方法名称 : CreateInstance(System.String,System.String,System.Int32,System.String,System.String,System.Boolean,System.String,System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "bizObjectId" | 业务对象的ID |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程版本号 |
| "instanceId" | 流程实例的ID，如果为空则由Engine自动生成一个 |
| "originator" | 发起人 |
| "isChildInstance" | 是否是子实例 |
| "parentInstanceID" | 如果是子实例，则该项为父实例的ID |
| "parentActivityName" | 如果是子实例，则该项为发起该实例的父实例的Activity的ID |
| "parentActivityTokenId" | 如果是子实例，则该项为发起该实例的父实例的TokenID |
| 返回值 |  |
| 如果创建成功则返回实例的ID，否则返回NullInstanceID |  |


方法名称 : CreateInstanceByDefault(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "bizObjectId" | 数据实例ID |
| "schemaCode" | 流程模板编码 |
| "originator" | 发起人 |
| 返回值 |  |
| instanceId |  |


方法名称 : GetWorkflowInstance(System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例的ID |
| 返回值 |  |
| 流程实例的上下文 |  |


方法名称 : GetWorkflowInstancesByBizObject(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 数据模型编码 |
| "bizObjectId" | 业务实例ID |
| 返回值 |  |
| 返回当前数据所有绑定的流程实例的集合 |  |


方法名称 : GetParentInstanceInfo(System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例的ID |
| 返回值 |  |
| 父流程实例信息 |  |


方法名称 : RemoveInstance(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 要删除的流程实例的ID |
| "autoUpdateBizObject" | 删除之后，是否需要更新BO.WorkflowInstanceId字段 |
| 返回值 |  |
| |  |


方法名称 : ChangeInstanceRemindState(System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | |
| 返回值 |  |
| |  |


方法名称 : SendMessage(H3.Workflow.Messages.Message)

| 参数 | 说明 |
| --- | --- |
| "message" | 发送给流程实例的消息 |
| 返回值 |  |
| 消息处理结果 |  |