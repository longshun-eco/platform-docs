---
title: "BizObjectState"
source: "https://help.h3yun.com/contents/373/393.html"
category: "開發者手冊 / 后端API / H3.DataModel / BizObjectState"
updated: 2025-12-16
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizObjectState
说明 : 业务对象的状态 
成员 : 

| 名称 | 说明 |
| --- | --- |
| Unloaded | 未加载的 |
| Loaded | 已加载 |
| LoadedNull | 已加载，但是加载的对象为Null |
| Removed | 已删除 |
| BulkCreating | 批量创建中：已经进入到了Bulk队列，但是未提交给数据库 |
| BulkUpdating | 批量更新中：已经进入到了Bulk队列，但是未提交给数据库 |
| BulkRemoving | 批量删除中：已经进入到了Bulk队列，但是未提交给数据库 |