---
title: "IOrganization"
source: "https://help.h3yun.com/contents/487/617.html"
category: "開發者手冊 / 后端API / H3.Organization / IOrganization"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : IOrganization
说明 : 组织结构接口，用于增删改查组织结构信息，整个组织结构的索引是完全建立在内存索引的基础上的，所以响应会非常快 属性 : 

| 名称 | 说明 |
| --- | --- |
| Company | 公司信息 |



方法名称 : GetCompany(H3.Organization.DomainType)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetUserCount(H3.Organization.DomainType,H3.Organization.State)

| 参数 | 说明 |
| --- | --- |
| "domainType" | |
| "state" | |
| 返回值 |  |
| |  |


方法名称 : GetUnits(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "ids" | 组织的ID |
| 返回值 |  |
| 组织对象 |  |


方法名称 : GetUnitNameTable(System.String\[\],H3.Organization.NameType)

| 参数 | 说明 |
| --- | --- |
| "ids" | 组织的ID |
| "type" | 名称的类型 |
| 返回值 |  |
| 如果参数是Null，那么返回Null；否则按照每个ID获得名称，不获取重复的记录，然后返回一个(ID, 全名称)的表 |  |


方法名称 : GetName(System.String,H3.Organization.NameType)

| 参数 | 说明 |
| --- | --- |
| "id" | 组织的ID |
| "type" | 组织的名称的类型 |
| 返回值 |  |
| 如果返回null，那么表示该单元不存在 |  |


方法名称 : GetUnitCopy(System.String)

| 参数 | 说明 |
| --- | --- |
| "id" | 组织的ID |
| 返回值 |  |
| 组织对象 |  |


方法名称 : GetUnitLevel(System.String)

| 参数 | 说明 |
| --- | --- |
| "id" | 组织ID |
| 返回值 |  |
| 组织的层次 |  |


方法名称 : UpdateSortKeys(System.Collections.Generic.Dictionary{System.String,System.Int32})

| 参数 | 说明 |
| --- | --- |
| "sortedUnits" | 新的排序，结构式(unitId, sortKey) |
| 返回值 |  |
| |  |


方法名称 : AddUnit(H3.Organization.Unit)

| 参数 | 说明 |
| --- | --- |
| "unit" | 要添加的对象 |
| 返回值 |  |
| 返回ID |  |


方法名称 : UpdateUnit(H3.Organization.Unit)

| 参数 | 说明 |
| --- | --- |
| "unit" | 具有新属性的Unit |
| 返回值 |  |
| 错误代码 |  |


方法名称 : RemoveUnit(System.String)

| 参数 | 说明 |
| --- | --- |
| "unitId" | 要删除的组织的ID |
| 返回值 |  |
| 删除的Unit的数量 |  |


方法名称 : RemoveUnits(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "unitIds" | 要删除的组织的Id |
| 返回值 |  |
| |  |


方法名称 : SearchUnits(System.String,H3.Organization.UnitType,System.String\[\],System.Int32,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "keyword" | 关键字 |
| "unitType" | 类型 |
| "unitIds" | 范围 |
| "fromNum" | 开始 |
| "toNum" | 结束 |
| 返回值 |  |
| |  |


方法名称 : GetManager(System.String,H3.Organization.ManagerType)

| 参数 | 说明 |
| --- | --- |
| "id" | 组织的ID |
| "type" | 经理类型 |
| 返回值 |  |
| 这个组织的经理 |  |


方法名称 : GetManagers(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "units" | 用户/组/OU/公司/群的ID数组 |
| 返回值 |  |
| 组织的经理 |  |


方法名称 : GetManagersByLevel(System.String\[\],System.Int32)

| 参数 | 说明 |
| --- | --- |
| "units" | 组织ID。如果组织是群，那么获得群的子对象，并针对各个子对象获得相应的跨级经理；如果是非群，那么直接获得跨级经理 |
| "level" | 级别，0表示公司，1表示公司的直接下属OU，依次类推 |
| 返回值 |  |
| 返回的经理没有重复值 |  |


方法名称 : GetManagersByRole(System.String\[\],System.String)

| 参数 | 说明 |
| --- | --- |
| "units" | 组织ID |
| "roleId" | 角色ID |
| 返回值 |  |
| 如果对象不存在,那么返回Null |  |


方法名称 : FindManagersByLevelRange(System.String\[\],System.Int32)

| 参数 | 说明 |
| --- | --- |
| "userIds" | 查找的组织范围起点 |
| "endLevel" | 用户职级 |
| 返回值 |  |
| 经理集合 |  |


方法名称 : GetParent(System.String)

| 参数 | 说明 |
| --- | --- |
| "id" | 组织的ID |
| 返回值 |  |
| 父组织的ID |  |


方法名称 : GetParentUnit(System.String)

| 参数 | 说明 |
| --- | --- |
| "id" | 组织的ID |
| 返回值 |  |
| 父组织 |  |


方法名称 : GetParentUnitByLevel(System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "id" | 子对象ID |
| "level" | 层次 |
| 返回值 |  |
| 父对象 |  |


方法名称 : GetParentUnitsByLevel(System.String\[\],System.Int32)

| 参数 | 说明 |
| --- | --- |
| "ids" | 子对象ID |
| "level" | 层次 |
| 返回值 |  |
| 父对象 |  |


方法名称 : GetParents(System.String,H3.Organization.UnitType,System.Boolean,H3.Organization.State)

| 参数 | 说明 |
| --- | --- |
| "id" | 子Unit |
| "parentUnitType" | 要获得的父/祖先的类型 |
| "recursive" | 是否递归 |
| "state" | 状态条件，如果要所有状态的组织，可以使用Unspecified |
| 返回值 |  |
| 父/祖先集合 |  |


方法名称 : GetMembers(System.String\[\],H3.Organization.State)

| 参数 | 说明 |
| --- | --- |
| "parents" | 父组织的id |
| "state" | 状态 |
| 返回值 |  |
| 隶属于父组织的成员 |  |


方法名称 : GetMemberUsers(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "units" | 父组织的id |
| 返回值 |  |
| 父组织中的所有用户子成员 |  |


方法名称 : GetChildren(System.String,H3.Organization.UnitType,System.Boolean,H3.Organization.State)

| 参数 | 说明 |
| --- | --- |
| "id" | 祖先的id |
| "childUnitType" | 作为一个过滤条件，只返回这种类型的Unit |
| "recursive" | 是否递归 |
| "state" | 状态条件，如果要所有状态的组织，可以使用Unspecified |
| 返回值 |  |
| 如果祖先是Company或者OrganizationUnit类型，那么递归/不递归返回下面的所有ChildUnitType类型的Unit；如果是Group，则不递归只返回他的下属成员；如果是User，则不递归返回Manager指向该User的Unit |  |


方法名称 : GetChildUnits(System.String\[\],H3.Organization.UnitType,System.Boolean,H3.Organization.State)

| 参数 | 说明 |
| --- | --- |
| "ids" | 祖先的id |
| "childUnitType" | 作为一个过滤条件，只返回这种类型的Unit |
| "recursive" | 是否递归 |
| "state" | 状态条件，如果要所有状态的组织，可以使用Unspecified |
| 返回值 |  |
| 如果祖先是Company或者OrganizationUnit类型，那么递归/不递归返回下面的所有ChildUnitType类型的Unit；如果是Group，则不递归只返回他的下属成员；如果是User，则不递归返回Manager指向该User的Unit |  |


方法名称 : GetChildrenByLevel(System.String,H3.Organization.UnitType,System.Int32,H3.Organization.State)

| 参数 | 说明 |
| --- | --- |
| "id" | 父对象 |
| "childUnitType" | 子对象类型 |
| "level" | 层级 |
| "state" | 状态条件，如果要所有状态的组织，可以使用Unspecified |
| 返回值 |  |
| 该层级的子组织 |  |


方法名称 : GetChildUnitsByLevel(System.String,H3.Organization.UnitType,System.Int32,H3.Organization.State)

| 参数 | 说明 |
| --- | --- |
| "id" | 父对象 |
| "childUnitType" | 子对象类型 |
| "level" | 层级 |
| "state" | 状态条件，如果要所有状态的组织，可以使用Unspecified |
| 返回值 |  |
| 该层级的子组织 |  |


方法名称 : IsAncestor(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "childId" | 子孙id |
| "ancestorId" | 祖先id |
| 返回值 |  |
| 如果是祖先关系则返回true，否则返回false |  |


方法名称 : GetUserPosts(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户ID |
| "includeInherited" | 包括继承的 |
| 返回值 |  |
| 用户的岗位 |  |


方法名称 : GetUserRoles(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户ID |
| "includeInherited" | 包括继承的 |
| 返回值 |  |
| 用户的角色 |  |


方法名称 : GetUserRoleIds(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户ID |
| "includeInherited" | 包括继承的 |
| 返回值 |  |
| 用户的角色ID |  |


方法名称 : GetAllRoles

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 所有的角色 |  |


方法名称 : GetPostServiceUnits(System.String,System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "roleId" | |
| "userId" | |
| "postId" | |
| 返回值 |  |
| |  |


方法名称 : UpdateUserRoles(System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "userId" | |
| "roleIds" | |
| 返回值 |  |
| |  |


方法名称 : UpdateRoleUsers(System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "roleId" | |
| "userIds" | |
| 返回值 |  |
| |  |


方法名称 : RemoveRoleUsers(System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "userIds" | |
| "roleId" | |
| 返回值 |  |
| |  |


方法名称 : InitOrgHierarchy

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Synchronize(System.String@)

| 参数 | 说明 |
| --- | --- |
| "messages" | |
| 返回值 |  |
| |  |


方法名称 : SynchronizeFirst(System.String)

| 参数 | 说明 |
| --- | --- |
| "suiteKey" | |
| 返回值 |  |
| |  |


方法名称 : GetChildUserSummaries(System.String,H3.Organization.UnitType,System.Int32,System.Int32,System.Boolean,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "unitId" | 部门或角色Id |
| "type" | 部门或角色 |
| "fromNum" | 开始行 |
| "toNum" | 结束行 |
| "includeManger" | 是否包括经理 |
| "count" | 总数量 |
| 返回值 |  |
| 用户 |  |