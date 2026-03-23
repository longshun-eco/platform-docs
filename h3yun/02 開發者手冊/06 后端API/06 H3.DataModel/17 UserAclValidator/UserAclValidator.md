---
title: "UserAclValidator"
source: "https://help.h3yun.com/contents/356/371.html"
category: "開發者手冊 / 后端API / H3.DataModel / UserAclValidator"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : UserAclValidator
说明 : 用户权限验证器 属性 : 

| 名称 | 说明 |
| --- | --- |
| Organization | 组织结构对象 |
| FunctionAclManager | 权限管理器 |
| BizObjectManager | 业务对象管理器 |
| UserId | 用户Id |
| User | 用户对象 |
| Posts | 该用户对应的岗位 |
| Roles | 该用户对应的角色 |
| RecursiveMemberOfs2 | 递归隶属于，包括所在公司、递归上级部门和本用户 |
| RecursiveOwnDepts | 我的部门，包括我所在的公司和递归上级部门 |
| IsAdministrator | 当前用户是否是管理员 |
| FunctionScopeTable | (FunctionCode.ToLower(), (Unit))，该用户针对某个功能可以访问的权限的列表。一个用户可能拥有多个角色，多个角色可能对同一个功能都有权限，在这里会自动去重 |
| FormActionCodeTable | 表单权限菜单，(SchemaCode, ActionCode\[\]) |
| ListViewActionCodeTable | 表单权限菜单，(SchemaCode, ActionCode\[\]) |
| FunctionNodeTable | 所有功能，包括没有权限的功能，格式是(FunctionCode.ToLower(), FunctionNode) |



构造方法名称 : #ctor(H3.Organization.IOrganization,H3.Acl.IFunctionAclManager,H3.DataModel.IBizObjectManager,System.String)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织结构管理器 |
| "functionAclManager" | 功能权限管理器 |
| "bizObjectManager" | 业务对象管理器 |
| "userId" | 用户Id |
| 返回值 |  |
| |  |


方法名称 : HasFunction(System.String)

| 参数 | 说明 |
| --- | --- |
| "functionCode" | 功能编码 |
| 返回值 |  |
| 如果具备该功能的权限，则返回true，否则返回false |  |


方法名称 : Initialize(H3.Organization.User,H3.Organization.OrgPost\[\],H3.Organization.OrgRole\[\],System.String\[\],System.String\[\],System.Collections.Generic.HashSet{System.String},System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{System.String}},System.Collections.Generic.Dictionary{System.String,System.String\[\]},System.Collections.Generic.Dictionary{System.String,System.String\[\]})

| 参数 | 说明 |
| --- | --- |
| "user" | |
| "posts" | |
| "roles" | |
| "recursiveMemberOfs2" | |
| "recursiveOwnDepts" | |
| "FunctionNodeTable" | |
| "functionScopeTable" | |
| "formActionCodeTable" | |
| "listViewActionCodeTable" | |
| 返回值 |  |
| |  |


方法名称 : GetFunctionScopes(System.String)

| 参数 | 说明 |
| --- | --- |
| "functionCode" | |
| 返回值 |  |
| |  |


方法名称 : GetMemberOfs(System.String,H3.Organization.UnitType,System.Boolean,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "unitId" | 组织ID |
| "unitType" | 隶属于的对象的类型范围 |
| "recursive" | 是否递归获得隶属于对象 |
| "includeSelf" | 是否包含自己 |
| 返回值 |  |
| 组织的隶属于 |  |


方法名称 : GetFolderAcls(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 文档库模式 |
| "folderId" | 文档库中的目录ID |
| 返回值 |  |
| 目录的权限设置 |  |


方法名称 : ValidateBizObjectAcl(H3.DataModel.UsageType,System.String,System.String,System.String,System.String,System.String\[\],H3.Acl.AclType)

| 参数 | 说明 |
| --- | --- |
| "type" | 数据模型的应用类型 |
| "schemaCode" | 数据模型编码 |
| "folderId" | 文档库ID |
| "ownerId" | 拥有者 |
| "ownerDept" | 所属部门 |
| "relatedMembers" | 相关人 |
| "aclType" | 权限类型 |
| 返回值 |  |
| 如果拥有该权限，则返回true，否则返回false |  |