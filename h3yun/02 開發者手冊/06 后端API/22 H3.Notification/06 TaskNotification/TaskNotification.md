---
title: "TaskNotification"
source: "https://help.h3yun.com/contents/668/751.html"
category: "開發者手冊 / 后端API / H3.Notification / TaskNotification"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : TaskNotification
说明 : 任务通知，当收到新任务或者任务需要提醒的时候进行任务通知 属性 : 

| 名称 | 说明 |
| --- | --- |
| TaskId | 任务的Id |
| Name | 任务的名称 |
| Summary | 任务的摘要 |
| SchemaCode | 任务绑定的业务对象的模式编码 |
| TargetType | 任务绑定的业务对象的模式编码 |
| TargetId | 任务链接的目标的Id |



构造方法名称 : #ctor(System.Boolean,System.String,System.String,System.String,System.String,System.String,System.String,H3.LinkTargetType,System.String)

| 参数 | 说明 |
| --- | --- |
| "isNew" | 如果是新任务通知则为true，如果是其他任务通知（比如任务到期通知）则为false |
| "sender" | 发送方，通常是任务的创建人 |
| "receiver" | 接收方 |
| "taskId" | 任务的Id |
| "name" | 任务的名称 |
| "summary" | 任务的摘要 |
| "schemaCode" | 任务绑定的业务对象的模式编码 |
| "targetType" | 任务链接的目标的类型 |
| "targetId" | 任务链接的目标的Id |
| 返回值 |  |
| |  |


方法名称 : Convert(H3.Settings.ISettingManager,H3.Organization.IOrganization,H3.Entry.IEntryManager,H3.App.IAppPackageManager)

| 参数 | 说明 |
| --- | --- |
| "settingManager" | 设置管理器 |
| "organization" | 组织机构管理器 |
| "entryManager" | 接入管理器 |
| "appPackageManager" | 应用包管理器 |
| 返回值 |  |
| 转换成的用户消息 |  |