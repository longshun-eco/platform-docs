---
title: "NamedItemSchemaCollection`1"
source: "https://help.h3yun.com/contents/449/658.html"
category: "開發者手冊 / 后端API / H3.Data / NamedItemSchemaCollection`1"
updated: 2025-12-19
tags:
  - h3yun
  - 開發者手冊
---
类名 : NamedItemSchemaCollection\`1
说明 : 命名项模式集合 属性 : 

| 名称 | 说明 |
| --- | --- |
| Items | 所有的命名项模式 |
| Count | 集合中包含的项的数量 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| Table | (Name.ToLower(), Item) |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Exists(System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 项名称 |
| 返回值 |  |
| 如果存在，则返回true，否则返回false |  |


方法名称 : Add(\`0)

| 参数 | 说明 |
| --- | --- |
| "item" | 项模式 |
| 返回值 |  |
| 如果项模式的名称合法，并且名称不重复，则返回true，否则返回false |  |


方法名称 : Remove(System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 项名称 |
| 返回值 |  |
| |  |


方法名称 : Clear

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 项名称 |
| 返回值 |  |
| 项模式 |  |


方法名称 : GetNamedItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 名称 |
| 返回值 |  |
| 项目模式 |  |


方法名称 : GetNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 所有的项名称 |  |


方法名称 : GetDataTableSupportedItems

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 所有数据表支持的项 |  |


方法名称 : GetDataType(System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 项名称 |
| 返回值 |  |
| 项类型 |  |


方法名称 : GetDisplayName(System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 项名称 |
| 返回值 |  |
| 显示名称 |  |


方法名称 : Update(System.String,\`0)

| 参数 | 说明 |
| --- | --- |
| "oldItemName" | 项的旧名称 |
| "newItemSchema" | 新的项模式 |
| 返回值 |  |
| 如果项不存在，或者存在重名的话，则返回false，否则返回true |  |