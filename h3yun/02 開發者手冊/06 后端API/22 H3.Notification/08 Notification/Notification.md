---
title: "Notification"
source: "https://help.h3yun.com/contents/670/758.html"
category: "開發者手冊 / 后端API / H3.Notification / Notification"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : Notification
说明 : 各种事件通知的基类 属性 : 

| 名称 | 说明 |
| --- | --- |
| Sender | 发送者 |
| Receiver | 接收者 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| Param\_TargetType | 常量：链接的目标的类型 |
| Param\_TargetId | 常量：链接的目标的Id |
| Param\_SchemaCode | 常量：链接的对象的业务对象模式编码 |
| Param\_TaskId | 常量：链接的对象的任务Id |
| Param\_WorkItemId | 常量：链接的对象的工作项Id |
| Param\_BizObjectId | 常量：链接的对象的对象Id |


构造方法名称 : #ctor(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "sender" | 发送者Id |
| "receiver" | 接收者Id |
| 返回值 |  |
| |  |


方法名称 : Convert(H3.Settings.ISettingManager,H3.Organization.IOrganization,H3.Entry.IEntryManager,H3.App.IAppPackageManager)

| 参数 | 说明 |
| --- | --- |
| "settingManager" | 设置管理器 |
| "organization" | 组织机构管理器 |
| "entryManager" | 集成管理器 |
| "appPackageManager" | 应用包管理器 |
| 返回值 |  |
| 转换成的用户消息 |  |


方法名称 : CreateMessages(H3.Notification.UserMessageType\[\],System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "types" | 用户消息的类型 |
| "sender" | 发送方 |
| "receiver" | 接收方 |
| "title" | 消息的标题 |
| "content" | 消息的内容 |
| "linkContent" | 消息的链接 |
| "appCode" | 应用的编码 |
| "messageId" | 消息的批次 |
| "linkUrl" | 消息的链接 |
| "solutionCode" | 解决方案编码 |
| 返回值 |  |
| 创建的用户消息 |  |


方法名称 : GetNotificationSolutionCode(System.String,H3.App.IAppPackageManager,System.String@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| "appPackageManager" | |
| "appCode" | |
| "sheetName" | |
| 返回值 |  |