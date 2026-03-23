---
title: "IIndexManager"
source: "https://help.h3yun.com/contents/469/667.html"
category: "開發者手冊 / 后端API / H3.Indexing / IIndexManager"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : IIndexManager
说明 : 索引管理器 
方法名称 : Search(H3.Indexing.UserSearchContext)

| 参数 | 说明 |
| --- | --- |
| "context" | 搜索关键词的上下文 |
| 返回值 |  |
| 搜索上下文，其中会返回结果集和当前的分页 |  |


方法名称 : GetTips(System.String)

| 参数 | 说明 |
| --- | --- |
| "keyword" | 搜索关键词 |
| 返回值 |  |
| 相关的关键词 |  |


方法名称 : Hit(System.String,H3.Indexing.DocumentType)

| 参数 | 说明 |
| --- | --- |
| "objectId" | 命中的对象的ID |
| "type" | |
| 返回值 |  |