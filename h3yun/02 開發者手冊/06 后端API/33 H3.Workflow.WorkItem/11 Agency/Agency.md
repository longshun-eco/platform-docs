---
title: "Agency"
source: "https://help.h3yun.com/contents/656/414.html"
category: "開發者手冊 / 后端API / H3.Workflow.WorkItem / Agency"
updated: 2025-12-21
tags:
  - h3yun
  - 開發者手冊
---
类名 : Agency
说明 : 用户工作项委托设置。当系统向用户A发送一个工作项的时候，会首先检查委托设置，如果存在委托，则发给委托人 属性 : 

| 名称 | 说明 |
| --- | --- |
| AgencyId | 委托ID |
| UserId | 委托人 |
| AgentId | 被委托人 |
| SchemaCode | 流程模板类型。委托关系创建之后，该属性不可更改。 |
| Originator | 发起人组织结构 |
| StartTime | 开始时间 |
| EndTime | 结束时间 |
| Effective | 对于当前时间是否生效 |
| Default | 是否是默认委托 |
| AgencyType | 委托的类型 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_UserId | 属性名称 |
| PropertyName\_AgentId | 属性名称 |
| PropertyName\_SchemaCode | 属性名称 |
| PropertyName\_Originator | 属性名称 |
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


构造方法名称 : #ctor(System.String,H3.Workflow.WorkItem.AgencyType,System.String,System.String,System.String,System.DateTime,System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "userId" | 要委托的用户 |
| "agencyType" | 委托模式 |
| "agentId" | 接受委托的用户 |
| "schemaCode" | 流程模板编码 |
| "originator" | 发起人所在组织的范围 |
| "startTime" | 开始时间 |
| "endTime" | 结束时间 |
| 返回值 |  |
| |  |


方法名称 : CheckType(H3.Workflow.WorkItem.AgencyType)

| 参数 | 说明 |
| --- | --- |
| "Type" | 要检查的类型 |
| 返回值 |  |
| 如果类型符合，则返回true，否则返回false |  |


方法名称 : Validate

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 如果验证合法，则返回true，否则返回false |  |