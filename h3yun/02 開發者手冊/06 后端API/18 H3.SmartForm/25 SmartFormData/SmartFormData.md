---
title: "SmartFormData"
source: "https://help.h3yun.com/contents/585/601.html"
category: "開發者手冊 / 后端API / H3.SmartForm / SmartFormData"
updated: 2025-12-16
tags:
  - h3yun
  - 開發者手冊
---
类名 : SmartFormData
说明 : 请求服务端传输的表单数据 属性 : 

| 名称 | 说明 |
| --- | --- |
| InstanceData | 流程数据 |
| FormDataType | 表单模式 |
| BizObject | 业务对象 |
| Item(System.String) | 索引器 |



构造方法名称 : #ctor(H3.IEngine,H3.SmartForm.SmartFormMode,H3.Workflow.Instance.WorkflowInstance,System.Int32,H3.Workflow.Template.WorkflowTemplate,System.String,System.String,System.String,H3.DataModel.BizObjectSchema,System.String,H3.Data.Serialization.VirtualObject,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{H3.DataModel.BizObjectFileHeader}},System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader},System.Collections.Generic.Dictionary{System.String,System.String})

| 参数 | 说明 |
| --- | --- |
| "engine" | 引擎实例 |
| "formMode" | 表单打开模式（编辑，只读，发起，打印） |
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


构造方法名称 : #ctor(H3.Organization.IOrganization,H3.Data.IDataDictManager,H3.DataModel.IBizObjectManager,H3.Workflow.Instance.IWorkflowInstanceManager,H3.Query,H3.Workflow.WorkItem.IWorkItemManager,H3.Workflow.Template.IWorkflowTemplateManager,H3.SmartForm.SmartFormMode,H3.Workflow.Instance.WorkflowInstance,System.Int32,H3.Workflow.Template.WorkflowTemplate,System.String,System.String,System.String,H3.DataModel.BizObjectSchema,System.String,H3.Data.Serialization.VirtualObject,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{H3.DataModel.BizObjectFileHeader}},System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader},System.Collections.Generic.Dictionary{System.String,System.String})

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构对象管理器 |
| "dataDictManager" | 数据字典管理器 |
| "bizObjectManager" | 业务对象管理器 |
| "workflowInstanceManager" | 流程实例管理器 |
| "query" | 查询数据库接口管理器 |
| "workItemManager" | 流程任务管理器 |
| "workflowTemplateManager" | 流程模板管理器 |
| "formMode" | 表单打开的模式（打开，编辑，查看，打印） |
| "workflowInstance" | 流程实例对象 |
| "tokenId" | 步骤ID |
| "workflowTemplate" | 流程模板对象 |
| "activityCode" | 活动编码 |
| "userId" | 用户ID |
| "userParentId" | 用户所属部门 |
| "schema" | 数据模型编码 |
| "bizObjectId" | 业务对象ID |
| "virtualObject" | 业务对象的数据集 |
| "fileTable" | 业务对象相关的文件 |
| "associatedBoTable" | 业务对象相关的关联对象信息表 |
| "unitNameTable" | 业务对象相关联的组织的Id名称对照表 |
| 返回值 |  |
| |  |