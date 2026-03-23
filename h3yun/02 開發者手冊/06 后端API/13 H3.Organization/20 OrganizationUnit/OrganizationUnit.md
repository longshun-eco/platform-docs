---
title: "OrganizationUnit"
source: "https://help.h3yun.com/contents/491/625.html"
category: "開發者手冊 / 后端API / H3.Organization / OrganizationUnit"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : OrganizationUnit
说明 : 组织单元，组织单元类似于公司架构下的部门，一个用户和一个组织单元只能挂在一个其他的组织单元或者公司下面。如果与活动目录同步的话，该类对应的活动目录中的组织单元 属性 : 

| 名称 | 说明 |
| --- | --- |
| UnitType | 类型 |
| DingTalkDepartmentId | 获取或设置Ding部门ID |
| WeChatDepartmentId | 获取或设置企业微信部门ID |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 数据库表名称 |
| ExternalTableName | 对应的表名称 |
| ExternalObjectIdPrefix | 外部前缀 |
| PropertyName\_DingTalkDepartmentId | DingTalk部门ID |
| PropertyName\_WeChatDepartmentId | 企业部门ID |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Organization.DomainType)

| 参数 | 说明 |
| --- | --- |
| "domainType" | 范围 |
| 返回值 |  |
| |  |


方法名称 : CreateExternalOrganizationUnit(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : IsExternalId(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectId" | |
| 返回值 |  |
| |  |


方法名称 : Validate(H3.Organization.IOrganizationValidator)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织结构接口，用来获得人员、OU、组等信息 |
| 返回值 |  |
| 如果合法则返回SUCCESS，否则返回错误代码 |  |


方法名称 : GetIndexableProperties(System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "requireUnique" | |
| 返回值 |  |
| |  |


方法名称 : GetIndexablePropertyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 索引字段的名称 |
| 返回值 |  |
| 索引的值 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |