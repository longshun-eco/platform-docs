---
title: "InstanceData"
source: "https://help.h3yun.com/contents/695/778.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance / InstanceData"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : InstanceData
说明 : 流程数据，他会统一调用数据项控制器、数据管理器等单元，然后给开放出一个最终的接口 属性 : 

| 名称 | 说明 |
| --- | --- |
| BizObjectManager | 获取bomanager |
| InstanceId | 获取当前流程实例ID |
| TokenId | 令牌ID |
| ActivityCode | 活动Code |
| UserId | 当前用户的Id |
| UserParentId | 当前用户的父ID |
| Workflow | 对应的流程模板 |
| SchemaCode | 业务对象模式编码 |
| Schema | 获取当前的业务对象 |
| BizObject | 获取当前数据模型 |
| Item(System.String) | 用于获得数据项 |
| WorkflowInstance | 该对象对应的流程上下文对象，该对象只有在被访问的时候才真实地从服务器上去获取，否则始终为空。 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| \_orgCache | 缓存用户对象信息，(UserId, User) |
| \_dataItemCache | 数据项缓存 |


构造方法名称 : #ctor(H3.IEngine,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "engine" | 流程引擎 |
| "instanceId" | 流程实例的Id |
| "userId" | 当前用户Id |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.IEngine,H3.Workflow.Instance.WorkflowInstance,System.String)

| 参数 | 说明 |
| --- | --- |
| "engine" | 流程引擎 |
| "workflowInstance" | 流程实例 |
| "userId" | 当前用户Id |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Organization.IOrganization,H3.Data.IDataDictManager,H3.Query,H3.DataModel.IBizObjectManager,H3.Workflow.Template.IWorkflowTemplateManager,H3.Workflow.Instance.IWorkflowInstanceManager,H3.Workflow.WorkItem.IWorkItemManager,H3.Workflow.Instance.WorkflowInstance,System.String)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "dataDictManager" | 数据字典管理器 |
| "query" | 查询管理器 |
| "bizObjectManager" | 业务对象管理器 |
| "workflowTemplateManager" | 流程模板管理器 |
| "workflowInstanceManager" | 流程实例管理器 |
| "workItemManager" | 任务管理器 |
| "workflowInstance" | 流程实例 |
| "userId" | 用户id |
| 返回值 |  |
| |  |


方法名称 : \_InstanceData(H3.Organization.IOrganization,H3.Data.IDataDictManager,H3.Query,H3.DataModel.IBizObjectManager,H3.Workflow.Template.IWorkflowTemplateManager,H3.Workflow.Instance.IWorkflowInstanceManager,H3.Workflow.WorkItem.IWorkItemManager,H3.Workflow.Instance.WorkflowInstance,System.String)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "dataDictManager" | 数据字典管理器 |
| "query" | 查询管理器 |
| "bizObjectManager" | 业务对象管理器 |
| "workflowTemplateManager" | 流程模板管理器 |
| "workflowInstanceManager" | 流程实例管理器 |
| "workItemManager" | 任务管理器 |
| "workflowInstance" | 流程实例 |
| "userId" | 用户id |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.IEngine,H3.Workflow.Instance.WorkflowInstance,System.Int32,H3.Workflow.Template.WorkflowTemplate,System.String,System.String,System.String,H3.DataModel.BizObjectSchema,System.String,H3.Data.Serialization.VirtualObject,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{H3.DataModel.BizObjectFileHeader}},System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader},System.Collections.Generic.Dictionary{System.String,System.String})

| 参数 | 说明 |
| --- | --- |
| "engine" | 引擎实例 |
| "workflowInstance" | 流程实例对象 |
| "tokenId" | 当前活动实例ID |
| "workflowTemplate" | 流程对象 |
| "activityCode" | 当前活动编码 |
| "userId" | 操作用户 |
| "userParentId" | 用户所属OU |
| "schema" | 数据模型编码 |
| "bizObjectId" | 业务实例数据Id |
| "virtualObject" | 业务对象的数据集 |
| "fileTable" | 业务对象相关的文件 |
| "associatedBoTable" | 业务对象相关联的对象 |
| "unitNameTable" | 业务对象相关联的组织的Id名称对照表 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Organization.IOrganization,H3.Data.IDataDictManager,H3.Query,H3.DataModel.IBizObjectManager,H3.Workflow.Template.IWorkflowTemplateManager,H3.Workflow.Instance.IWorkflowInstanceManager,H3.Workflow.WorkItem.IWorkItemManager,H3.Workflow.Instance.WorkflowInstance,System.Int32,H3.Workflow.Template.WorkflowTemplate,System.String,System.String,System.String,H3.DataModel.BizObjectSchema,System.String,H3.Data.Serialization.VirtualObject,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{H3.DataModel.BizObjectFileHeader}},System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader},System.Collections.Generic.Dictionary{System.String,System.String})

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "dataDictManager" | 数据字典管理器 |
| "query" | 查询管理器 |
| "bizObjectManager" | 业务对象管理器 |
| "workflowTemplateManager" | 流程模板管理器 |
| "workflowInstanceManager" | 流程实例管理器 |
| "workItemManager" | 任务管理器 |
| "workflowInstance" | 流程实例对象 |
| "tokenId" | 当前活动实例ID |
| "workflowTemplate" | 流程对象 |
| "activityCode" | 当前活动编码 |
| "userId" | 操作用户 |
| "userParentId" | 用户所属OU |
| "schema" | 数据模型编码 |
| "bizObjectId" | 业务实例数据Id |
| "virtualObject" | 业务对象的数据集 |
| "fileTable" | 业务对象相关的文件 |
| "associatedBoTable" | 业务对象相关联的对象 |
| "unitNameTable" | 业务对象相关联的组织的Id名称对照表 |
| 返回值 |  |
| |  |


方法名称 : IsKeyword(System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 项名称 |
| 返回值 |  |
| 如果是关键字，则返回true，否则返回false |  |


方法名称 : ParseText(System.String)

| 参数 | 说明 |
| --- | --- |
| "sourceData" | 源数据字符串 |
| 返回值 |  |
| 解析后的字符串 |  |


方法名称 : CopyInstanceData(System.String,System.String,System.String,System.Int32,System.String\[\],System.String\[\],System.Boolean\[\],System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "destSchemaCode" | 目标业务对象模式编码 |
| "destBizObjectId" | 业务对象Id |
| "destInstanceId" | 目标流程ID |
| "destTokenId" | 目标步骤ID |
| "sourcePropertyNames" | 源数据项名称 |
| "destPropertyNames" | 目标数据项名称 |
| "overwrite" | 如果是true，那么是覆盖模式；否则，是添加模式 |
| "ignoreException" | 如果出现异常是否停止复制 |
| 返回值 |  |
| 如果成功则返回SUCCESS，否则返回错误ID |  |


方法名称 : Calculate(System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "expression" | 要计算的表达式 |
| "errorMessage" | 错误信息 |
| 返回值 |  |
| 计算结果 |  |


方法名称 : Calculate\`\`1(System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "expression" | 要计算的表达式 |
| "errorMessage" | 错误信息 |
| 返回值 |  |
| 计算结果 |  |