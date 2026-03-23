---
title: "EngineConfig"
source: "https://help.h3yun.com/contents/328/332.html"
category: "開發者手冊 / 后端API / H3.Clusterware / EngineConfig"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : EngineConfig
说明 : 引擎的相关设置 属性 : 

| 名称 | 说明 |
| --- | --- |
| Code | 逻辑单元编码 |
| VesselCode | 运行的服务器的编码 |
| UnitState | 逻辑单元的状态 |
| CreatedTime | 创建时间 |
| DbType | 数据库的类型 |
| DbServer | 服务器地址 |
| DbInstanceId | 数据库实例 |
| DbUser | 引擎访问数据库的登录用户名 |
| DbPassword | 登录密码 |
| CompanyName | 公司名称 |
| InitialUserCode | 初始用户编码 |
| DingTalkCorpId | DingTalk企业号 |
| WeChatCorpId | 企业微信corpId |
| ContactName | 服务器地址 |
| UsageType | 引擎模式 |
| IsDeveloper | 是否是开发者 |
| DevCode | 开发者模式编码 |
| EntryType | 接入类型 |
| CommandFactory | 访问数据库用的接口 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_Code | 属性名称 |
| PropertyName\_VesselCode | 属性名称 |
| PropertyName\_UnitState | 属性名称 |
| PropertyName\_CreatedTime | 属性名称 |
| PropertyName\_DbInstanceId | 属性名称 |
| PropertyName\_DbUser | 属性名称 |
| PropertyName\_DbPassword | 属性名称 |
| PropertyName\_CompanyName | 属性名称 |
| PropertyName\_InitialUserCode | 属性名称 |
| PropertyName\_DingTalkCorpId | 属性名称 |
| PropertyName\_WeChatCorpId | 属性名称 |
| PropertyName\_ContactName | 属性名称 |
| PropertyName\_UsageType | 是否为引擎模式的属性名称 |
| PropertyName\_DevCode | 属性名称 |
| PropertyName\_EntryType | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetDbName

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 数据库名称 |  |


方法名称 : GetDbConnString

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 数据库连接字符串 |  |


方法名称 : GetUniquePropertyName

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetPropertyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| |  |


方法名称 : GetFoundEachOtherPropertyName

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetFoundByUniquePropertyName

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : CopyFrom(H3.Clusterware.EngineConfig)

| 参数 | 说明 |
| --- | --- |
| "config" | 复制的源 |
| 返回值 |  |
| |  |


方法名称 : ToString

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 字段信息 |  |


方法名称 : CreateCommand

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| command |  |


方法名称 : IsTest

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |