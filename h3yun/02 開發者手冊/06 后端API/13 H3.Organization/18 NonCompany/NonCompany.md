---
title: "NonCompany"
source: "https://help.h3yun.com/contents/489/622.html"
category: "開發者手冊 / 后端API / H3.Organization / NonCompany"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : NonCompany
说明 : 非Company的Unit的基类 属性 : 

| 名称 | 说明 |
| --- | --- |
| ParentId | 父对象ID |
| CompanyId | 公司ID |
| Visibility | 是否允许同时属于多个父组 |
| State | 状态 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName\_ParentId | 属性名称 |
| PropertyName\_Visibility | 属性名称 |
| PropertyName\_State | 属性名称 |


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
| "domainType" | |
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
| 如果验证成功则返回Success，否则返回错误代码 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |
 |