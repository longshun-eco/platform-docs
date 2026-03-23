---
title: "IOrganizationValidator"
source: "https://help.h3yun.com/contents/488/619.html"
category: "開發者手冊 / 后端API / H3.Organization / IOrganizationValidator"
updated: 2025-12-21
tags:
  - h3yun
  - 開發者手冊
---
类名 : IOrganizationValidator
说明 : 组织机构管理器 
方法名称 : GetUnit(System.String)

| 参数 | 说明 |
| --- | --- |
| "id" | 组织的Id |
| 返回值 |  |
| 组织对象 |  |


方法名称 : GetParentUnits(System.String,H3.Organization.UnitType,System.Boolean,H3.Organization.State)

| 参数 | 说明 |
| --- | --- |
| "id" | 子Unit |
| "parentUnitType" | 要获得的父/祖先的类型 |
| "recursive" | 是否递归 |
| "state" | 状态条件，如果要所有状态的组织，可以使用Unspecified |
| 返回值 |  |
| 父/祖先集合 |  |


方法名称 : GetUnitsByProperty(H3.Organization.DomainType,H3.Organization.UnitType,System.String,System.String,H3.Organization.State)

| 参数 | 说明 |
| --- | --- |
| "domainType" | 范围 |
| "type" | 类型 |
| "propertyName" | 属性名称 |
| "propertyValue" | 属性值 |
| "state" | 状态 |
| 返回值 |  |
| |  |


方法名称 : GetUnitByProperty(H3.Organization.DomainType,H3.Organization.UnitType,System.String,System.String,H3.Organization.State)

| 参数 | 说明 |
| --- | --- |
| "domainType" | 范围 |
| "type" | 类型 |
| "propertyName" | 属性名称 |
| "propertyValue" | 属性值 |
| "state" | 状态 |
| 返回值 |  |
| |
 |