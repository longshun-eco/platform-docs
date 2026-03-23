---
title: "InstanceFinishedNotification"
source: "https://help.h3yun.com/contents/663/738.html"
category: "開發者手冊 / 后端API / H3.Notification / InstanceFinishedNotification"
updated: 2025-12-15
tags:
  - h3yun
  - 開發者手冊
---
类名 : InstanceFinishedNotification
说明 : 流程实例的结束通知 属性 : 

| 名称 | 说明 |
| --- | --- |
| InstanceId | 流程Id |
| BizObjectId | 流程对应的业务对象的Id |
| Name | 流程实例的名称 |
| Summary | 流程的摘要 |
| SchemaCode | 流程对应的业务对象模式的编码 |



构造方法名称 : #ctor(System.String,System.String,System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "sender" | 发送人，也就是流程实例的发起人 |
| "receiver" | 接收人，也就是流程实例的发起人 |
| "name" | 流程实例的名称 |
| "summary" | 流程的摘要 |
| "schemaCode" | 流程对应的业务对象模式的编码 |
| "instanceId" | 流程Id |
| "bizObjectId" | 流程对应的业务对象的Id |
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