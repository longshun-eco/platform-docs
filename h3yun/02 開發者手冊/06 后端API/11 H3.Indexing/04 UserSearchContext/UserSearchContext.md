---
title: "UserSearchContext"
source: "https://help.h3yun.com/contents/470/670.html"
category: "開發者手冊 / 后端API / H3.Indexing / UserSearchContext"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : UserSearchContext
说明 : 用户调用索引的上下文，这里会记录用户搜索的条件和分页情况 属性 : 

| 名称 | 说明 |
| --- | --- |
| DataAclScope | 要搜索的对象的权限范围，比如：所有对象、仅限于该用户能访问的等 |
| SchemaCode | 要搜索的对象的业务对象模式 |
| OnlyNameField | 是否仅搜索名称字段，如果仅搜索名称字段，则会很快返回 |
| StartTime | 对象创建的时间大于等于开始时间 |
| EndTime | 对象创建的时间小于等于结束时间 |
| Keyword | 搜索的关键词 |
| WordTable | 关键词的分词 |
| FromRow | 请求搜索的起始行 |
| PageSize | 分页的页面的大小 |
| ToRow | 返回搜索的结束行号 |
| CurrentResult | 本次搜索的搜索结果 |
| IsEnd | 搜索是否到了最后一页了 |
| FoundCount | 所有符合条件的目标的总数 |



构造方法名称 : #ctor(H3.Acl.DataAclScope,System.String,System.Boolean,System.DateTime,System.DateTime,System.Int32,System.String)

| 参数 | 说明 |
| --- | --- |
| "dataAclScope" | 要搜索的对象的权限范围，比如：所有对象、仅限于该用户能访问的等 |
| "schemaCode" | 要搜索的对象的业务对象模式 |
| "onlyNameField" | 是否仅搜索名称字段，如果仅搜索名称字段，则会很快返回 |
| "startTime" | 对象创建的开始时间 |
| "endTime" | 对象创建的结束时间 |
| "pageSize" | 搜索对象的页面的大小 |
| "keyword" | 搜索的关键词 |
| 返回值 |  |