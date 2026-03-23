---
title: "SharingNotification"
source: "https://help.h3yun.com/contents/666/745.html"
category: "開發者手冊 / 后端API / H3.Notification / SharingNotification"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : SharingNotification
说明 : 设置分享的通知 属性 : 

| 名称 | 说明 |
| --- | --- |
| SchemaCode | 业务对象模式编码 |
| TargetType | 关联的对象的类型 |
| TargetId | 分享的对象的Id |
| TargetName | 分享的对象的名称 |



构造方法名称 : #ctor(System.String,System.String,System.String,H3.LinkTargetType,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "sender" | 发送分享的人 |
| "receiver" | 接收分享的人 |
| "schemaCode" | 业务对象模式编码 |
| "targetType" | 分享的对象的类型 |
| "targetId" | 分享的对象的Id |
| "targetName" | 分享的对象的名称 |
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