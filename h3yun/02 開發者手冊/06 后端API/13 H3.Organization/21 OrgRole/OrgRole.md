---
title: "OrgRole"
source: "https://help.h3yun.com/contents/492/628.html"
category: "開發者手冊 / 后端API / H3.Organization / OrgRole"
updated: 2025-12-18
tags:
  - h3yun
  - 開發者手冊
---
类名 : OrgRole
说明 : 组织结构的角色。其中：系统中默认会有两个系统角色：系统管理员和所有用户。系统管理员角色下面必须至少有一个用户；所有用户角色必须包含所有用户 属性 : 

| 名称 | 说明 |
| --- | --- |
| UnitType | 组织类型 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| ExternalTableName | 表名称 |
| AdminRoleId | 管理员角色的Id |
| AdminRoleName | 管理员角色的名称 |
| AdminRoleCode | 管理员角色的编码 |
| UserRoleId | 用户角色的Id |
| UserRoleName | 用户角色的名称 |
| UserRoleCode | 用户角色的编码 |
| ExternalObjectIdPrefix | 外部角色的Id前缀 |
| ExternalUserRoleId | 外部用户的角色Id |
| ExternalUserRoleName | 用户角色的名称 |
| AnonymousRoleId | 匿名用户角色ID |
| AnonymousRoleName | 匿名用户角色名称 |


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
| "domainType" | 组织机构隶属于的域类型 |
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
| "organization" | |
| 返回值 |  |
| |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |