---
title: "IFunctionAclManager"
source: "https://help.h3yun.com/contents/302/298.html"
category: "開發者手冊 / 后端API / H3.Acl / IFunctionAclManager"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : IFunctionAclManager
说明 : 功能权限管理 
方法名称 : AddAcl(H3.Acl.FunctionAcl)

| 参数 | 说明 |
| --- | --- |
| "acl" | 权限对象 |
| 返回值 |  |
| 返回添加权限是否成功 |  |


方法名称 : DeleteAcl(System.String)

| 参数 | 说明 |
| --- | --- |
| "aclId" | 权限对象Id |
| 返回值 |  |
| |  |


方法名称 : GetAcl(System.String)

| 参数 | 说明 |
| --- | --- |
| "aclId" | 权限对象Id |
| 返回值 |  |
| 返回权限对象 |  |


方法名称 : GetRoleAcls(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "roles" | 角色Id |
| 返回值 |  |
| (Role.RoleId.ToLower(), FunctionAcl\[\])每个角色所拥有的功能权限 |  |


方法名称 : GetFunctionAcls(System.String)

| 参数 | 说明 |
| --- | --- |
| "functionCode" | 功能权限编码 |
| 返回值 |  |
| 相应的所有的权限设置 |  |


方法名称 : UpdateAcl(H3.Acl.FunctionAcl)

| 参数 | 说明 |
| --- | --- |
| "acl" | 菜单权限对象 |
| 返回值 |  |