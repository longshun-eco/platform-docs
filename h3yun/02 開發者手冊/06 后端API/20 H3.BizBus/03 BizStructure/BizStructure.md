---
title: "BizStructure"
source: "https://help.h3yun.com/contents/630/717.html"
category: "開發者手冊 / 后端API / H3.BizBus / BizStructure"
updated: 2025-12-21
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizStructure
说明 : 业务结构，只是用来传递可自解析的数据 属性 : 

| 名称 | 说明 |
| --- | --- |
| Item(System.String) | 根据属性名称获得属性值，设置值的时候，检查类型 |
| Schema | 业务结构模式 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| Table | (属性名称, 属性值) |


构造方法名称 : #ctor(H3.BizBus.BizStructureSchema)

| 参数 | 说明 |
| --- | --- |
| "schema" | 业务结构模式 |
| 返回值 |  |
| |  |


方法名称 : AddValue(System.String,System.Object)

| 参数 | 说明 |
| --- | --- |
| "name" | 属性名称 |
| "value" | 属性值 |
| 返回值 |  |
| 如果参数合法，并且原来的记录不存在，那么添加，并返回true；否则返回false |  |


方法名称 : \_GetItemSchema(System.String)

| 参数 | 说明 |
| --- | --- |
| "Name" | 项名称 |
| 返回值 |  |
| 项模式 |  |


方法名称 : GetValueXml(System.String)

| 参数 | 说明 |
| --- | --- |
| "name" | 项名称 |
| 返回值 |  |
| Xml值 |  |


方法名称 : SetValueXml(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "name" | 业务结构的属性 |
| "xml" | 值的XML |
| 返回值 |  |
| |  |


方法名称 : ParseValueXml(H3.BizBus.BizStructureSchema,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schema" | 业务结构模式 |
| "name" | 项名称 |
| "xml" | Xml值 |
| 返回值 |  |
| 业务结构项的值 |  |


方法名称 : ReadXml(System.Xml.XmlReader)

| 参数 | 说明 |
| --- | --- |
| "reader" | |
| 返回值 |  |
| |  |


方法名称 : \_ReadXml(System.Xml.XmlReader,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "reader" | Xml Reader |
| "collectionTag" | 集合标签 |
| "itemTag" | 项标签 |
| 返回值 |  |
| |  |


方法名称 : \_WriteXml(System.Xml.XmlWriter,System.String\[\],System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "writer" | Xml Writer |
| "names" | 要写入的项的名称 |
| "CollectionTag" | 集合标签 |
| "ItemTag" | 项标签 |
| 返回值 |  |
| |  |


方法名称 : GetValueXml

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 将转换的结构是：Item1, Item2, Item3这样的结构 |  |


构造方法名称 : #ctor(H3.BizBus.BizStructureSchema,System.String)

| 参数 | 说明 |
| --- | --- |
| "Schema" | 业务结构模式 |
| "Xml" | 业务结构值的XML |
| 返回值 |  |
| |  |


方法名称 : GetHashCode

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 返回Hash编码 |  |


方法名称 : ToString

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Equals(System.Object)

| 参数 | 说明 |
| --- | --- |
| "obj" | |
| 返回值 |  |
| |  |