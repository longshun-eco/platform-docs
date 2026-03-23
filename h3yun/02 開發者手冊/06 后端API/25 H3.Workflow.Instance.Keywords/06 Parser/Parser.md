---
title: "Parser"
source: "https://help.h3yun.com/contents/703/796.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance.Keywords / Parser"
updated: 2025-12-16
tags:
  - h3yun
  - 開發者手冊
---
类名 : Parser
说明 : 关键字解析器 属性 : 

| 名称 | 说明 |
| --- | --- |
| WorkflowManager | 流程管理器 |
| WorkflowInstanceManager | 流程实例管理器 |
| Organization | 组织管理器 |
| WorkItemManager | 任务管理器 |
| Query | 查询管理器 |



构造方法名称 : #ctor(H3.IEngine)

| 参数 | 说明 |
| --- | --- |
| "engine" | 流程引擎 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Workflow.Instance.IWorkflowInstanceManager,H3.Workflow.Template.IWorkflowTemplateManager,H3.Organization.IOrganization,H3.Workflow.WorkItem.IWorkItemManager,H3.Query)

| 参数 | 说明 |
| --- | --- |
| "workflowInstanceManager" | |
| "workflowManager" | |
| "organization" | |
| "workItemManager" | |
| "query" | |
| 返回值 |  |
| |  |


方法名称 : IsKeyword(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键字 |
| 返回值 |  |
| bool |  |


方法名称 : IsParticipant(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键字 |
| 返回值 |  |
| bool |  |


方法名称 : GetDisplayName(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键字 |
| 返回值 |  |
| string |  |


方法名称 : ParseValue(System.String,H3.Workflow.Instance.WorkflowInstance,System.String,System.Int32,System.Int32,System.String,System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit})

| 参数 | 说明 |
| --- | --- |
| "itemName" | 项名称 |
| "context" | 流程实例管理器 |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程模板版本号 |
| "tokenId" | 令牌ID，或者叫步骤ID，流程实例每走过一个活动该ID会自动加1。令牌与活动是N:1的关系 |
| "filler" | 当前用户，构造该函数的用户，用于获得当前用户的信息 |
| "orgCache" | 用于缓存已经访问过的组织结构对象 |
| 返回值 |  |
| object |  |


方法名称 : GetBizDataType(System.String)

| 参数 | 说明 |
| --- | --- |
| "word" | 关键字 |
| 返回值 |  |
| BizDataType |  |


方法名称 : GetKeywords

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| string\[\] |  |


方法名称 : CreateTree(H3.Workflow.Instance.Keywords.KeyWordNode)

| 参数 | 说明 |
| --- | --- |
| "parentNode" | 父节点 |
| 返回值 |  |
| |  |


方法名称 : AddChild(H3.Workflow.Instance.Keywords.KeyWordNode,System.String)

| 参数 | 说明 |
| --- | --- |
| "parent" | 父节点 |
| "text" | 文本 |
| 返回值 |  |
| |  |


方法名称 : AddParticipants(System.String\[\],System.Collections.Generic.List{System.String})

| 参数 | 说明 |
| --- | --- |
| "newParticipants" | 新参与者 |
| "participantList" | 参与者列表 |
| 返回值 |  |
| |  |


方法名称 : GetUnit(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| Unit |  |


方法名称 : GetUserEmail(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUnitParentId(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUnitDirectManager(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUserFullName(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUnitName(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUnitLevel(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| int |  |


方法名称 : GetUserTitle(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUserIdNumber(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUserEmployeeNumber(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUserEmployeeRank(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| int |  |


方法名称 : GetUserMobile(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUserOfficePhone(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUserLoginName(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| string |  |


方法名称 : GetUserBirthday(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| DateTime |  |


方法名称 : GetUserEntryDate(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| DateTime |  |


方法名称 : GetUserDepartureDate(System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.String)

| 参数 | 说明 |
| --- | --- |
| "orgCache" | 组织缓存 |
| "unitId" | 组织id |
| 返回值 |  |
| DateTime |  |