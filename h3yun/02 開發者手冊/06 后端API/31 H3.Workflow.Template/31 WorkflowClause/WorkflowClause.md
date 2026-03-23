---
title: "WorkflowClause"
source: "https://help.h3yun.com/contents/735/563.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / WorkflowClause"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkflowClause
说明 : 流程模板族，根据流程模板类型与流程模板名称可以指定一个流程模板族，一个流程模板族中包含多个流程模板，每个流程模板的版本号是不同的 属性 : 

| 名称 | 说明 |
| --- | --- |
| SortKey | 排序值 |
| DisplayName | 显示名称 |
| SchemaCode | 获取或设置数据模型编码 |
| CurrentNewVersion | 下一个流程模板的版本号 |
| DefaultVersion | 默认版本号，除非指定具体的流程模板版本号，否则发起新的流程实例的时候，始终以这个版本号为准 |
| State | 流程模板状态 |
| IconFileName | 获取或设置图标的文件名称 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_SortKey | 属性名称 |
| PropertyName\_DisplayName | 属性名称 |
| PropertyName\_SchemaCode | 数据模型编码 |
| DefaultNewVersion | 流程模板族的第一个版本号 |
| PropertyName\_CurrentNewVersion | 属性名称 |
| PropertyName\_DefaultVersion | 属性名称 |
| PropertyName\_State | 属性名称 |
| PropertyName\_IconFileName | 图标的文件名称，ERROR, 检查下这个属性是否还需要 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | SchemaCode |
| "workflowName" | 流程模板名称 |
| "sortKey" | 排序键 |
| 返回值 |  |
| |  |


方法名称 : MatchState(H3.Workflow.Template.WorkflowState)

| 参数 | 说明 |
| --- | --- |
| "workflowState" | 要匹配的状态 |
| 返回值 |  |
| 如果当前状态与目标状态匹配，则返回true，否则返回false |  |


方法名称 : GetKeyNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetKeyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "KeyName" | |
| 返回值 |  |
| |
 |