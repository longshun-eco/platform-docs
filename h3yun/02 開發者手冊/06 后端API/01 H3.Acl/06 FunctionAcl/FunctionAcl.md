---
title: "FunctionAcl"
source: "https://help.h3yun.com/contents/303/300.html"
category: "開發者手冊 / 后端API / H3.Acl / FunctionAcl"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : FunctionAcl
说明 : 功能权限 属性 : 

| 名称 | 说明 |
| --- | --- |
| RoleId | 角色Id |
| FunctionCode | 功能编码 |
| ScopeType | 该角色在自己的组织结构下拥有的数据权限 |
| ListViewActions | 列表有权限的按钮 |
| FormActions | 有权限的按钮 |
| Valid | 是否合法 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_RoleId | 属性名称 |
| PropertyName\_FunctionCode | 属性名称 |
| PropertyName\_ScopeType | 属性名称 |
| PropertyName\_ListViewActions | 有权限的按钮 |
| PropertyName\_FormActions | 表单有权限的按钮 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "roleId" | 用户ID，实际上，这个也可以使一个OU ID或者其他组织结构的ID |
| "functionCode" | 功能代码或菜单类别ID |
| "createdBy" | 创建人 |
| 返回值 |  |
| |
 |