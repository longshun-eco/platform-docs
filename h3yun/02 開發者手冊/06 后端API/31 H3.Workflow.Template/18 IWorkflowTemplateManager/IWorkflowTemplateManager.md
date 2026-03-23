---
title: "IWorkflowTemplateManager"
source: "https://help.h3yun.com/contents/722/515.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / IWorkflowTemplateManager"
updated: 2025-12-14
tags:
  - h3yun
  - 開發者手冊
---
类名 : IWorkflowTemplateManager
说明 : 流程模板管理器，用于发布、获得、更新流程模板信息 
方法名称 : GetDraftTemplate(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| 返回流程模板草稿对象 |  |


方法名称 : SaveDraftTemplate(H3.Workflow.Template.WorkflowTemplate)

| 参数 | 说明 |
| --- | --- |
| "workflowTemplate" | 流程模板草稿对象 |
| 返回值 |  |
| 返回操作是否成功 |  |


方法名称 : GetDefaultWorkflow(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| 返回已发布的流程模板对象 |  |


方法名称 : GetDefaultWorkflowHeaders(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "schemaCodes" | 流程模板编码集合 |
| 返回值 |  |
| 获取已发布的流程模板头信息集合 |  |


方法名称 : GetClause(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| 流程模板族 |  |


方法名称 : GetClauses(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "schemaCodes" | 流程包编码集合 |
| 返回值 |  |
| 返回流程模板运行参数集合 |  |


方法名称 : RemoveClause(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| |  |


方法名称 : GetPublishedTemplate(System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程版本号 |
| 返回值 |  |
| 返回流程模板对象 |  |


方法名称 : GetPublishedTemplateHeader(System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程版本号 |
| 返回值 |  |
| 返回流程模板头信息 |  |


方法名称 : GetPublishedTemplateHeaders(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| 返回指定流程模板的所有已发布历史版本集合 |  |


方法名称 : GetWorkflowVersions(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| 返回指定流程模板的所有版本号集合 |  |


方法名称 : GetWorkflowDefaultVersion(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| 流程模板的当前默认版本号 |  |


方法名称 : SetWorkflowDefaultVersion(System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| "defaultVersion" | |
| 返回值 |  |
| 如果设置成功，则返回0，否则返回错误代码 |  |


方法名称 : GetWorkflowNewVersion(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| 流程模板的下一个版本号 |  |


方法名称 : SetWorkflowState(System.String,H3.Workflow.Template.WorkflowState)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| "state" | 流程模板的状态 |
| 返回值 |  |
| 如果设置成功则返回0，否则返回错误代码 |  |


方法名称 : GetWorkflowState(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| 获得流程模板的状态 |  |


方法名称 : GetWorkflowCount

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 流程模板的数量 |  |


方法名称 : RemoveWorkflowTemplate(System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程模板版本号 |
| 返回值 |  |
| |  |


方法名称 : GetClauseDisplayName(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| 返回值 |  |
| 流程模板的显示名称 |  |


方法名称 : GetTemplateDisplayName(System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程模板版本号 |
| 返回值 |  |
| 流程模板的显示名称 |  |


方法名称 : UpdateClause(H3.Workflow.Template.WorkflowClause)

| 参数 | 说明 |
| --- | --- |
| "workflowClause" | 流程模板运行参数对象 |
| 返回值 |  |
| 返回修改是否成功,0:表示成功 |  |


方法名称 : AddClause(H3.Workflow.Template.WorkflowClause)

| 参数 | 说明 |
| --- | --- |
| "workflowClause" | 流程模板运行参数对象 |
| 返回值 |  |
| 返回添加是否成功,0:表示成功 |  |