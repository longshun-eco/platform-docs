---
title: "BizStructureSchema"
source: "https://help.h3yun.com/contents/631/720.html"
category: "開發者手冊 / 后端API / H3.BizBus / BizStructureSchema"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizStructureSchema
说明 : 业务结构的Schema 属性 : 

| 名称 | 说明 |
| --- | --- |
| Code | 标记这个业务结构是来自.Net/Java/SAP/其他系统的哪个类，这个类名称会被用来生成H3中对应的Schema的SchemaCode |



成员 : 

| 名称 | 说明 |
| --- | --- |
| DefaultReturnItemName | 业务系统中返回值可以放在这个字段上 |
| ReturnValueItemName | 业务系统中的返回值映射到H3的Schema上的字段的字段名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Add(H3.BizBus.ItemSchema)

| 参数 | 说明 |
| --- | --- |
| "item" | 业务结构的项目 |
| 返回值 |  |
| 如果添加成功，则返回true；否则返回false |  |