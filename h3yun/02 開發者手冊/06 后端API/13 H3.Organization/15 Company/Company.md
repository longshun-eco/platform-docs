---
title: "Company"
source: "https://help.h3yun.com/contents/486/612.html"
category: "開發者手冊 / 后端API / H3.Organization / Company"
updated: 2025-12-21
tags:
  - h3yun
  - 開發者手冊
---
类名 : Company
说明 : 公司，在整个组织结构中是有且仅有一个的，也是组织结构中最高层级的 属性 : 

| 名称 | 说明 |
| --- | --- |
| UnitType | 类型 |
| CompanyId | 公司的Id |



成员 : 

| 名称 | 说明 |
| --- | --- |
| DefaultCompanyId | 公司的Id，所有引擎的公司Id都等于这个值 |
| InternalCompanyId | 公司的Id，所有引擎的公司Id都等于这个值 |
| ExternalCompanyId | 外部公司的Id，所有引擎的外部公司Id都等于这个值 |
| ExternalCompanyName | 外部公司的名称,这是一个暂时的值 |
| TableName | 表名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : CreateInternalCompany

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : CreateExternalCompany

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | 对象的名称 |
| 返回值 |  |
| 键值对 |  |