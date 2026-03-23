---
title: "ItemSchema"
source: "https://help.h3yun.com/contents/634/723.html"
category: "開發者手冊 / 后端API / H3.BizBus / ItemSchema"
updated: 2025-12-14
tags:
  - h3yun
  - 開發者手冊
---
类名 : ItemSchema
说明 : 每个属性的Schema 属性 : 

| 名称 | 说明 |
| --- | --- |
| ChildSchema | 子对象模式 |



构造方法名称 : #ctor(System.String,System.String,H3.Data.BizDataType,H3.BizBus.BizStructureSchema)

| 参数 | 说明 |
| --- | --- |
| "name" | 项名称 |
| "displayName" | 显示名称 |
| "bizDataType" | 类型 |
| "childSchema" | 如果类型是BizStructure或者BizStructureArray，那么该属性有效，表示子结构 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,H3.Data.BizDataType,System.Int32,System.Object)

| 参数 | 说明 |
| --- | --- |
| "name" | 项名称 |
| "displayName" | 显示名称 |
| "bizDataType" | 类型 |
| "maxLength" | 最大长度，比如字符串类型，是可以设置长度限制的 |
| "DefaultValue" | 默认值 |
| 返回值 |  |
| |  |


方法名称 : Update(System.String,System.String,H3.Data.BizDataType,H3.BizBus.BizStructureSchema)

| 参数 | 说明 |
| --- | --- |
| "name" | 项名称 |
| "displayName" | 显示名称 |
| "bizDataType" | 类型 |
| "childSchema" | 如果类型是BizStructure或者BizStructureArray，那么该属性有效，表示子结构 |
| 返回值 |  |
| |  |


方法名称 : Update(System.String,System.String,H3.Data.BizDataType,System.Int32,System.Object)

| 参数 | 说明 |
| --- | --- |
| "name" | 项名称 |
| "displayName" | 显示名称 |
| "bizDataType" | 类型 |
| "maxLength" | 最大长度，比如字符串类型，是可以设置长度限制的 |
| "defaultValue" | 默认值 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |