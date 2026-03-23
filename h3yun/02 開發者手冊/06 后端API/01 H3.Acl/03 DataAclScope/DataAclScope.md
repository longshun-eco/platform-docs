---
title: "DataAclScope"
source: "https://help.h3yun.com/contents/300/295.html"
category: "開發者手冊 / 后端API / H3.Acl / DataAclScope"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : DataAclScope
说明 : 用户有权限访问的对象，仅限于DataList和Workflow类型的字段，不包括DocLib 属性 : 

| 名称 | 说明 |
| --- | --- |
| IsAdmin | 是否是管理员 |
| RecursiveMemberOfs2 | 递归的隶属于，包括：公司、部门、角色和自己 |
| CompanySchemas | 当前用户在整个公司范围内有权限的schema，格式是(schemaCode)。比如，如果当前用户是管理员，那么这里就会包括所有Schema的SchemaCode |
| DeptSchemas | 当前用户拥有部门权限的Schema，格式是(schemaCode, (deptId))。比如，当前用户是A和B部门对于Schema1的管理员权限，那么这里会记录(Schema1, (A, B)) |
| OwnSchemas | 当前用户拥有自己的权限的Schema，格式是(schemaCode)。比如，当前用户能够访问schema1和schema2中的自己创建的对象，那么这里记录的是(schem1, schema2) |
| OwnerDepts | 我所在的部门和我所在部门的子部门，包括所在公司，但是不包括自己 |
| OwnerId | 本人Id |



构造方法名称 : #ctor(System.String,System.Boolean,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户的Id |
| "isAdmin" | 该用户是否具有管理员权限 |
| "memberOfs" | 该用户的全部隶属于，包括：公司、部门、角色和自己 |
| 返回值 |  |
| |  |


方法名称 : GetSchemaScopeType(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 业务对象模式编码 |
| 返回值 |  |
| 拥有的权限范围 |  |