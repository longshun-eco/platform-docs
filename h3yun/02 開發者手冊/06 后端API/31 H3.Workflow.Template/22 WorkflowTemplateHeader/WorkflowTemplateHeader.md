---
title: "WorkflowTemplateHeader"
source: "https://help.h3yun.com/contents/726/530.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / WorkflowTemplateHeader"
updated: 2025-12-14
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkflowTemplateHeader
说明 : 流程模板的摘要，通常为了减少网络传输流量，在这里只传输流程模板的摘要 属性 : 

| 名称 | 说明 |
| --- | --- |
| SchemaCode | 业务对象模式编码 |
| DisplayName | 显示名称: 它来自于WorkflowClause.DisplayName |
| StartActivityCode | 开始活动编码,即"开始"后的第一个活动编码 |
| WorkflowVersion | 流程模板版本号 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName\_SchemaCode | 业务对象模式编码 |
| PropertyName\_StartActivityCode | 开始活动编码,即"开始"后的第一个活动编码 |
| PropertyName\_WorkflowVersion | 版本号 |


方法名称 : GetHeader(System.Data.DataRow)

| 参数 | 说明 |
| --- | --- |
| "row" | 附件头记录 |
| 返回值 |  |
| 附件头对象 |  |


方法名称 : GetHeaders(System.Data.DataTable)

| 参数 | 说明 |
| --- | --- |
| "table" | 头记录表 |
| 返回值 |  |
| 头对象 |  |


方法名称 : GetProperties

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 属性名称 |  |