---
title: "IEntryManager"
source: "https://help.h3yun.com/contents/471/655.html"
category: "開發者手冊 / 后端API / H3.Entry / IEntryManager"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : IEntryManager
说明 : 第三方平台管理器 
方法名称 : AddDingTalkAppRelation(H3.DingTalk.DingTalkAppRelation)

| 参数 | 说明 |
| --- | --- |
| "appRelation" | |
| 返回值 |  |
| |  |


方法名称 : GetDingTalkAppRelation(System.String)

| 参数 | 说明 |
| --- | --- |
| "AppId" | |
| 返回值 |  |
| |  |


方法名称 : GetISVAppRelation(System.String)

| 参数 | 说明 |
| --- | --- |
| "dingAppId" | dingAppId |
| 返回值 |  |
| |  |


方法名称 : RemoveOrgListenter(System.String)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : RemoveAllOrgListenter

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : CheckEntryInfo

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetSuiteBySolutionCode(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | |
| 返回值 |  |
| |  |


方法名称 : GetCorpSecret

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : UpdateCorpSecret(System.String)

| 参数 | 说明 |
| --- | --- |
| "secret" | |
| 返回值 |  |
| |  |


方法名称 : EnsureDingTalkIsvInfo(H3.DingTalk.DingTalkSuite,H3.DingTalk.AuthInfo,System.String\[\]@)

| 参数 | 说明 |
| --- | --- |
| "suite" | 套件信息 |
| "authInf" | 授权信息 |
| "installAppCodes" | 安装的应用编码 |
| 返回值 |  |
| |  |


方法名称 : RegisterOrgListenter

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : ReAuth(System.String)

| 参数 | 说明 |
| --- | --- |
| "suiteKey" | |
| 返回值 |  |
| |  |


方法名称 : GetPrintDingTalkApprelation(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | |
| 返回值 |  |
| |  |


方法名称 : GetFirstSuiteKey

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : SetWeChatSuiteEnterprise(H3.WeChat.WeChatSuite,H3.Entry.EntryAuthInfo,System.String\[\]@)

| 参数 | 说明 |
| --- | --- |
| "suite" | 套件 |
| "authInfo" | 授权信息 |
| "installAppCodes" | 安装的应用编码 |
| 返回值 |  |
| |  |


方法名称 : Relieve(System.String)

| 参数 | 说明 |
| --- | --- |
| "suitKey" | |
| 返回值 |  |
| |  |


方法名称 : GetAccessToken(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "suitId" | 套件Id |
| "forceRefresh" | 强制刷新 |
| 返回值 |  |
| |  |


方法名称 : ChangeWeChatAuth(System.String,System.String\[\]@)

| 参数 | 说明 |
| --- | --- |
| "suiteKey" | 套件key |
| "installAppCodes" | 安装的应用编码 |
| 返回值 |  |
| |  |


方法名称 : RemoveAppRelationByAppCode(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | |
| 返回值 |  |
| |  |


方法名称 : SendMessages(H3.Notification.UserMessage\[\],System.Collections.Generic.Dictionary{System.String,System.String})

| 参数 | 说明 |
| --- | --- |
| "messages" | 消息 |
| "senderNameTable" | id与name |
| 返回值 |  |
| |  |


方法名称 : GetDepartmentUsers(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "id" | 获取的部门id |
| "fetchChild" | 1/0：是否递归获取子部门下面的成员 |
| 返回值 |  |
| |  |


方法名称 : GetDepartmentSimpleUsers(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "id" | 获取的部门id |
| "fetchChild" | 1/0：是否递归获取子部门下面的成员 |
| 返回值 |  |
| |  |


方法名称 : CreateUser(H3.Organization.User,H3.Organization.Unit)

| 参数 | 说明 |
| --- | --- |
| "unit" | |
| "parent" | |
| 返回值 |  |
| |  |


方法名称 : UpdateUser(H3.Organization.User,H3.Organization.Unit)

| 参数 | 说明 |
| --- | --- |
| "unit" | |
| "parent" | |
| 返回值 |  |
| |  |


方法名称 : GetUser(System.String)

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户Id |
| 返回值 |  |
| |  |


方法名称 : RemoveUser(H3.Organization.Unit)

| 参数 | 说明 |
| --- | --- |
| "user" | 用户Id |
| 返回值 |  |
| |  |


方法名称 : RemoveUsers(H3.WeChat.WeChatUserIds)

| 参数 | 说明 |
| --- | --- |
| "userIds" | 用户Ids |
| 返回值 |  |
| |  |


方法名称 : CreateDepartment(H3.Organization.Unit,H3.Organization.Unit,H3.Organization.Unit)

| 参数 | 说明 |
| --- | --- |
| "unit" | |
| "parent" | |
| "manager" | |
| 返回值 |  |
| |  |


方法名称 : UpdateDepartment(H3.Organization.Unit,H3.Organization.Unit,H3.Organization.Unit)

| 参数 | 说明 |
| --- | --- |
| "unit" | |
| "parent" | |
| "manager" | |
| 返回值 |  |
| |  |


方法名称 : RemoveDepartment(H3.Organization.Unit)

| 参数 | 说明 |
| --- | --- |
| "department" | |
| 返回值 |  |
| |  |


方法名称 : GetDepartments(System.String)

| 参数 | 说明 |
| --- | --- |
| "departmentId" | |
| 返回值 |  |
| |  |


方法名称 : GetClusterType

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetDefaultUserMessageType

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : RemoveMicroApp(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | |
| 返回值 |  |
| |  |


方法名称 : CheckSignature(System.String)

| 参数 | 说明 |
| --- | --- |
| "signature" | |
| 返回值 |  |
| |  |


方法名称 : RefreshAccessToken(System.String)

| 参数 | 说明 |
| --- | --- |
| "suiteKey" | 套件key |
| 返回值 |  |