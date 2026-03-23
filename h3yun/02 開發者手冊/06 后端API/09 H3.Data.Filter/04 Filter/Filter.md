---
title: "Filter"
source: "https://help.h3yun.com/contents/458/688.html"
category: "開發者手冊 / 后端API / H3.Data.Filter / Filter"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : Filter
说明 : 过滤器，类似于SQL的SELECT语句，用于GetList方法获得满足条件的对象 属性 : 

| 名称 | 说明 |
| --- | --- |
| FromRowNum | 从第N条记录开始，基数是0，不含第N条 |
| ToRowNum | 到第M条，基数是0，不包含第M条 |
| Matcher | 该对象的匹配条件 |
| SortByCollection | 过滤器的排序方法 |
| ReturnItems | 要返回的列的集合，如果不为空，则表示只需要返回其中的列；否则，则表示采用默认的返回方式。这个属性与ReturnColumns是相通的，差别仅仅是这个不显示别名 |
| ReturnColumns | 要返回的列的集合，如果不为空，则表示只需要返回其中的列；否则，则表示采用默认的返回方式。这个属性与ReturnItems是相通的，差别仅仅是这个显示别名 |
| RequireCount | 是否需要返回符合条件的记录的总数，通常对于分页显示记录的时候，是需要获得总数的 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| DefaultMaxSize | 一次请求，最大的返回记录的数量 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : AddSortBy(System.String,H3.Data.Filter.SortDirection)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 排序的字段的名称 |
| "direction" | 从大到小或者从小到大 |
| 返回值 |  |
| 如果添加成功，则返回true，否则返回false |  |


方法名称 : AddSortBy(H3.Data.Filter.SortBy)

| 参数 | 说明 |
| --- | --- |
| "sortBy" | 排序字段的信息 |
| 返回值 |  |
| 如果没有重复的排序，则返回true，否则返回false |  |


方法名称 : RemoveSortBy(System.Int32)

| 参数 | 说明 |
| --- | --- |
| "index" | 要删除的排序索引号 |
| 返回值 |  |
| 如果删除成功，则返回true，否则返回false |  |


方法名称 : GetReferencdProperties(H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "schema" | 业务对象模式 |
| 返回值 |  |
| 引用的所有的业务对象模式的属性 |  |


方法名称 : GetReferencdProperties(System.Collections.Generic.List{System.String},H3.DataModel.BizObjectSchema,H3.Data.Filter.Matcher)

| 参数 | 说明 |
| --- | --- |
| "referencedProperties" | 引用的属性 |
| "schema" | 业务模型编码 |
| "matcher" | 匹配单元 |
| 返回值 |  |
| |  |


方法名称 : Validate

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 校验通过返回true，否则返回false |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlDocument" | xml文档 |
| "xmlElement" | xml元素 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlElement" | xml元素 |
| 返回值 |  |