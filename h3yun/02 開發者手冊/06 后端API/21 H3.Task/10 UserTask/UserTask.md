---
title: "UserTask"
source: "https://help.h3yun.com/contents/645/779.html"
category: "開發者手冊 / 后端API / H3.Task / UserTask"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : UserTask
说明 : 用户任务，通过这个用户任务来统一系统中的所有任务，并进行统一的提醒。为了提升性能，这个对象做了特殊处理，该对象的ObjectId等于绑定的TargetId 属性 : 

| 名称 | 说明 |
| --- | --- |
| Sender | 任务的发送方 |
| Name | 任务的名称 |
| Summary | 任务的摘要 |
| UserId | 需要提醒的用户 |
| TaskType | 任务的类型 |
| TaskState | 任务的状态 |
| ReminderType | 提醒的类型 |
| RecurrenceType | 重复的类型 |
| AlertTime | 提醒时间 |
| AlertState | 提醒的状态 |
| TargetType | 关联的目标的类型 |
| AppCode | 应用编码 |
| SchemaCode | 关联的目标的SchemaCode |
| TargetId | 关联的目标的Id |
| TargetName | 绑定的对象的名称 |
| StartTime | 开始时间 |
| EndTime | 截止时间 |
| UserName | 用户名称 |
| RuleId | 触发该任务的规则Id |
| SenderName | ERROR, 这个属性干嘛用？ |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_Sender | 属性名称 |
| PropertyName\_Name | 属性名称 |
| PropertyName\_Summary | 属性名称 |
| PropertyName\_UserId | 属性名称 |
| PropertyName\_TaskType | 属性名称 |
| PropertyName\_TaskState | 属性名称 |
| PropertyName\_ReminderType | 属性名称 |
| PropertyName\_RecurrenceType | 属性名称 |
| PropertyName\_AlertTime | 属性名称 |
| PropertyName\_AlertState | 属性名称 |
| PropertyName\_TargetType | 属性名称 |
| PropertyName\_AppCode | 属性名称 |
| PropertyName\_SchemaCode | 属性名称 |
| PropertyName\_TargetId | 属性名称 |
| PropertyName\_TargetName | 属性名称 |
| PropertyName\_StartTime | 属性名称 |
| PropertyName\_EndTime | 属性名称 |
| PropertyName\_RuleId | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.String,System.String,H3.LinkTargetType,System.String,System.String,System.String,System.String,System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "sender" | 创建任务的人 |
| "userId" | 接收任务的人 |
| "appCode" | 这个任务对应的App的ID |
| "schemaCode" | 任务绑定的业务对象的模式编码 |
| "targetType" | 任务绑定的对象的类型 |
| "targetId" | 任务绑定的对象的ID |
| "targetName" | 任务绑定的对象的名称 |
| "taskName" | 任务的名称 |
| "taskSummary" | 任务的摘要 |
| "endTime" | 任务的截止时间 |
| 返回值 |  |
| |  |


方法名称 : CreateTask(System.String,System.String,System.String,System.String,H3.LinkTargetType,System.String,System.String,System.String,System.String,System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "sender" | 创建任务的人 |
| "userId" | 接收任务的人 |
| "appCode" | 这个任务对应的App的ID |
| "schemaCode" | 任务绑定的业务对象的模式编码 |
| "targetType" | 任务绑定的对象的类型 |
| "targetId" | 任务绑定的对象的ID |
| "targetName" | 任务绑定的对象的名称 |
| "taskName" | 任务的名称 |
| "taskSummary" | 任务的摘要 |
| "endTime" | 任务的截止时间 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.String,System.String,H3.LinkTargetType,System.String,System.String,System.String,System.String,H3.Task.RecurrenceType,System.DateTime,System.DateTime,System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "sender" | 创建日程的人 |
| "userCode" | 接收日程的人 |
| "appCode" | 对应的App的Code |
| "schemaCode" | 绑定的业务对象的模式编码 |
| "targetType" | 绑定的对象的类型 |
| "targetId" | 任务绑定的对象的ID |
| "targetName" | 任务绑定的对象的名称 |
| "alertTime" | 提醒的事件 |
| "name" | 任务的名称 |
| "summary" | 任务的摘要 |
| "recurrenceType" | 重复的类型 |
| "startTime" | 日程的开始时间 |
| "endTime" | 日程的截止时间 |
| 返回值 |  |
| |  |


方法名称 : CreateCalendar(System.String,System.String,System.String,System.String,H3.LinkTargetType,System.String,System.String,System.String,System.String,H3.Task.RecurrenceType,System.DateTime,System.DateTime,System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "sender" | 创建日程的人 |
| "userCode" | 接收日程的人 |
| "appCode" | 对应的App的ID |
| "schemaCode" | 绑定的业务对象的模式编码 |
| "targetType" | 绑定的对象的类型 |
| "targetId" | 任务绑定的对象的ID |
| "targetName" | 任务绑定的对象的名称 |
| "alertTime" | 提醒的事件 |
| "name" | 任务的名称 |
| "summary" | 任务的摘要 |
| "recurrenceType" | 重复的类型 |
| "startTime" | 日程的开始时间 |
| "endTime" | 日程的截止时间 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.String,System.String,H3.LinkTargetType,System.String,System.String,System.String,H3.Task.RecurrenceType,System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "sender" | 创建提醒的人 |
| "userId" | 接收提醒的人 |
| "appCode" | 对应的App的ID |
| "schemaCode" | 绑定的业务对象的模式编码 |
| "targetType" | 绑定的对象的类型 |
| "targetId" | 任务绑定的对象的ID |
| "recurrenceType" | 重复的类型 |
| "alertTime" | 提醒的事件 |
| "name" | 任务的名称 |
| "summary" | 任务的摘要 |
| 返回值 |  |
| |  |


方法名称 : CreateReminder(System.String,System.String,System.String,System.String,H3.LinkTargetType,System.String,System.String,System.String,H3.Task.RecurrenceType,System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "sender" | 创建提醒的人 |
| "userId" | 接收提醒的人 |
| "appCode" | 对应的App的ID |
| "schemaCode" | 绑定的业务对象的模式编码 |
| "targetType" | 绑定的对象的类型 |
| "targetId" | 任务绑定的对象的ID |
| "recurrenceType" | 重复的类型 |
| "alertTime" | 提醒的事件 |
| "name" | 任务的名称 |
| "summary" | 任务的摘要 |
| 返回值 |  |
| |  |


方法名称 : GetKeyNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 内存索引键名称 |  |


方法名称 : GetKeyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "keyName" | 索引键名称 |
| 返回值 |  |
| 索引键值 |  |