---
title: "UserContext"
source: "https://help.h3yun.com/contents/627/698.html"
category: "開發者手冊 / 后端API / H3.Web / UserContext"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : UserContext
说明 : 用户权限验证器 属性 : 

| 名称 | 说明 |
| --- | --- |
| IsDeveloper | 开发者 |
| UserId | 用户Id |
| User | 用户对象 |
| IsAdministrator | 是否管理员 |
| IsAnonymous | 是否是匿名用户 |
| Language | 多语言 |
| AgencyIdentityType | 委托类型 |
| FormActionCodes | 有权限的表单按钮 |
| ListViewActionCodes | 有权限的列表按钮 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| \_IsDeveloper | 用于缓存验证，以免每次都去访问数据库 |


构造方法名称 : #ctor(System.String,System.Boolean,H3.Organization.User,System.Boolean,System.String\[\],System.String\[\],System.Boolean,System.Collections.Generic.Dictionary{System.String,System.Object},H3.Data.FileServiceType)

| 参数 | 说明 |
| --- | --- |
| "engineCode" | 引擎编码 |
| "isDeveloper" | 是开发者 |
| "user" | 当前用户 |
| "isAdministrator" | 是管理员 |
| "formActionCodes" | 当前表单按钮权限 |
| "listViewActionCodes" | 当前列表按钮权限 |
| "isAnonymous" | 是匿名用户 |
| "portalSettings" | 网站设置 |
| "fileServiceType" | 存储类型 |
| 返回值 |  |
| |  |


方法名称 : GetThumbnailUrl(System.String)

| 参数 | 说明 |
| --- | --- |
| "fileId" | |
| 返回值 |  |
| |  |


方法名称 : GetLocalTime(System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "ServerTime" | 服务器时间 |
| 返回值 |  |
| 本地时间 |  |


方法名称 : GetServerTime(System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "LocalTime" | 本地时间 |
| 返回值 |  |
| 服务器时间 |  |


方法名称 : GetLocalTimeText(System.DateTime,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "ServerTime" | 服务器系统时间 |
| "IsHighPrecision" | 是否高精度显示，如果是高精度显示，格式则是日期 + 时间，否则则只有日期 |
| 返回值 |  |
| 本地时间的字符串 |  |


方法名称 : GetLocalTimeText(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "ServerTimeText" | 服务器系统时间 |
| "IsHighPrecision" | 是否高精度显示，如果是高精度显示，格式则是日期 + 时间，否则则只有日期 |
| 返回值 |  |
| 本地时间的字符串 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | |
| 返回值 |  |
| |  |