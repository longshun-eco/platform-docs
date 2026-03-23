---
title: "UserTaskRule"
source: "https://help.h3yun.com/contents/642/750.html"
category: "開發者手冊 / 后端API / H3.Task / UserTaskRule"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : UserTaskRule
说明 : 用户任务，通过这个用户任务来统一系统中的所有任务，并进行统一的提醒。为了提升性能，这个对象做了特殊处理，该对象的ObjectId等于绑定的TargetId 属性 : 

| 名称 | 说明 |
| --- | --- |
| SchemaCode | 关联的目标的SchemaCode |
| CreatedBy | 创建人，如果执行过程中发生错误，那么会发送消息给该人 |
| ConditionExpression | 生效的条件，这里是一个表达式，BizObject计算出这个表达式的值 |
| ActionType | 如果满足生效条件，那么这里触发要做的动作 |
| Receivers | 接收方，这里面每一项都可以是一个表达式 |
| RecurrenceType | 重复的类型 |
| AlertTime | 如果是要创建任务，那么这里指定从哪个属性中读取任务的结束时间 |
| OffsetTime | 偏移时间，json格式{"offsetDay":"-1","fixedTime":"09:00"} |
| TimeType | 时间类型 |
| StartTime | 开始时间 |
| EndTime | 截止时间 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_SchemaCode | 属性名称 |
| PropertyName\_CreatedBy | 属性名称 |
| PropertyName\_ConditionExpression | 属性名称 |
| PropertyName\_ActionType | 属性名称 |
| PropertyName\_Receivers | 属性名称 |
| PropertyName\_RecurrenceType | 属性名称 |
| PropertyName\_AlertTime | 属性名称 |
| PropertyName\_OffsetTime | 属性名称 |
| PropertyName\_TimeType | 属性名称 |
| PropertyName\_StartTime | 属性名称 |
| PropertyName\_EndTime | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
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