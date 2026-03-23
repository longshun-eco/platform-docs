---
title: "WorkflowUtility"
source: "https://help.h3yun.com/contents/725/527.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / WorkflowUtility"
updated: 2025-12-15
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkflowUtility
说明 : 流程的帮助类 
成员 : 

| 名称 | 说明 |
| --- | --- |
| SerialTable\_SN | SN字段 |
| SerialTable\_Code | Code字段 |
| SerialTable\_Name | 名称字段 |
| SerialTable\_Post | post字段 |


方法名称 : GetSerialTable(H3.Workflow.Template.WorkflowTemplate)

| 参数 | 说明 |
| --- | --- |
| "workflowTemplate" | 流程模板 |
| 返回值 |  |
| 流程模板的活动顺序表 |  |


方法名称 : IsTimeSpanConvertible(System.String,H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "item" | 字段 |
| "schema" | 业务对象模式 |
| 返回值 |  |
| 如果可以转换为时间段，则返回true，否则返回fales |  |