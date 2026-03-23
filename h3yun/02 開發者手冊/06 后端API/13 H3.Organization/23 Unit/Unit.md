---
title: "Unit"
source: "https://help.h3yun.com/contents/494/633.html"
category: "開發者手冊 / 后端API / H3.Organization / Unit"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : Unit
说明 : 组织机构的基本单元，所有组织结构中的元素都继承于他 属性 : 

| 名称 | 说明 |
| --- | --- |
| CompanyId | 所属的公司的Id |
| DomainType | 范围 |
| Name | 名称 |
| Description | 组织的描述 |
| UnitId | 唯一ID |
| UnitType | 类型 |
| Code | 编码，必填，一旦填写，必须唯一 |
| ManagerId | 经理 |
| CreatedTime | 创建时间 |
| ModifiedTime | 修改时间 |
| SortKey | 排序键值 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| NullId | 空单元ID |
| PathSeparator | 路径的分隔符 |
| NameMaxLen | 名称属性的最大长度 |
| PropertyName\_Name | 属性名称 |
| PropertyName\_Description | 属性名称 |
| PropertyName\_Code | 属性名称 |
| PropertyName\_ManagerId | 属性名称 |
| PropertyName\_ModifiedTime | 属性名称 |
| PropertyName\_SortKey | 属性名称 |
| UnspecifiedLevel | 未指定的级别，该常量可以用于查询 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : StringEquals(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "v1" | |
| "v2" | |
| 返回值 |  |
| |  |


方法名称 : GetScopeType(System.String)

| 参数 | 说明 |
| --- | --- |
| "unitId" | |
| 返回值 |  |
| |  |


方法名称 : GetExternalUnitType(System.String)

| 参数 | 说明 |
| --- | --- |
| "unitId" | |
| 返回值 |  |
| |  |


方法名称 : ReferTo(System.String)

| 参数 | 说明 |
| --- | --- |
| "unitId" | 被引用的对象的ID |
| 返回值 |  |
| 如果参数为Null或者""，那么返回False；如果参数为this.UnitId，那么返回true；否则检查其他属性是否等于该值。这个判断是区分大小写的 |  |


方法名称 : Validate(H3.Organization.IOrganizationValidator)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织结构接口，用来获得人员、OU、组等信息 |
| 返回值 |  |
| 如果验证成功，则返回SUCCESS，否则返回错误代码 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |