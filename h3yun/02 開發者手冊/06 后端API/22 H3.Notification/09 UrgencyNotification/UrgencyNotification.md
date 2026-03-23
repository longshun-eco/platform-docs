---
title: "UrgencyNotification"
source: "https://help.h3yun.com/contents/671/760.html"
category: "開發者手冊 / 后端API / H3.Notification / UrgencyNotification"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : UrgencyNotification
说明 : 催办的时候发送的通知 属性 : 

| 名称 | 说明 |
| --- | --- |
| WorkItemId | 工作项Id |
| DisplayName | 任务的名称 |
| Content | 催办的内容 |
| SchemaCode | 任务绑定的业务对象的模式编码 |



构造方法名称 : #ctor(System.String,System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "sender" | 发送方，通常是任务的创建人 |
| "receiver" | 接收方 |
| "workItemId" | 工作项Id |
| "displayName" | 任务的名称 |
| "content" | 催办的内容 |
| "schemaCode" | 任务绑定的业务对象的模式编码 |
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