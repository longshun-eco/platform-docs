---
title: "OrgPost"
source: "https://help.h3yun.com/contents/483/603.html"
category: "開發者手冊 / 后端API / H3.Organization / OrgPost"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : OrgPost
说明 : 组织结构的岗位，OrgPost.ParentId指向的就是角色 属性 : 

| 名称 | 说明 |
| --- | --- |
| UnitType | 组织的类型 |
| UserId | 用户ID |
| RoleId | 角色的ID |
| Depts | 对应的部门，默认是空，表示是本部门；如果不为空，则表示这几个部门对应的角色是该用户；对于管理员角色，这个属性必须为空，因为管理员不分部门 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| ExternalTableName | 表名称 |
| ExternalObjectIdPrefix | 外部岗位的Id前缀 |
| PropertyName\_UserId | 属性名称 |
| PropertyName\_Depts | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Organization.DomainType,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "domainType" | 组织机构隶属于的域类型 |
| "roleId" | 角色Id |
| "userId" | 用户Id |
| 返回值 |  |
| |  |


方法名称 : IsExternalId(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectId" | id |
| 返回值 |  |
| |  |


方法名称 : Validate(H3.Organization.IOrganizationValidator)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| 返回值 |  |
| 如果验证合法则返回Success，否则返回错误代码 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |