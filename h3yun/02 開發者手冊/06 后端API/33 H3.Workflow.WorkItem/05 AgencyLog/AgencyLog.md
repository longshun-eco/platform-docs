---
title: "AgencyLog"
source: "https://help.h3yun.com/contents/650/392.html"
category: "開發者手冊 / 后端API / H3.Workflow.WorkItem / AgencyLog"
updated: 2025-12-17
tags:
  - h3yun
  - 開發者手冊
---
类名 : AgencyLog
说明 : 用户工作项委托设置。当系统向用户A发送一个工作项的时候，会首先检查委托设置，如果存在委托，则发给委托人 属性 : 

| 名称 | 说明 |
| --- | --- |
| UserId | 委托人 |
| AgentId | 被委托人 |
| SchemaCode | 流程模板编码。委托关系创建之后，该属性不可更改。 |
| Originator | 发起人组织结构范围 |
| Operation | 操作方式 |
| StartTime | 开始时间 |
| EndTime | 结束时间 |
| AgencyType | 委托的类型 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_UserId | 属性名称 |
| PropertyName\_AgentId | 属性名称 |
| PropertyName\_SchemaCode | 属性名称 |
| PropertyName\_Originator | 属性名称 |
| PropertyName\_Operation | 属性名称 |
| PropertyName\_StartTime | 属性名称 |
| PropertyName\_EndTime | 属性名称 |
| PropertyName\_AgencyType | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Workflow.WorkItem.AgencyOperation,H3.Workflow.WorkItem.Agency)

| 参数 | 说明 |
| --- | --- |
| "operation" | 操作类型 |
| "agency" | 委托的内容 |
| 返回值 |  |
| |  |