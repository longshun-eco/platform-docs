---
title: "WorkItemState"
source: "https://help.h3yun.com/contents/660/432.html"
category: "開發者手冊 / 后端API / H3.Workflow.WorkItem / WorkItemState"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkItemState
说明 : 工作项的状态 
成员 : 

| 名称 | 说明 |
| --- | --- |
| Waiting | 处于等待的状态 |
| Working | 处于正在工作中的状态 |
| Finished | 处于完成状态 |
| Canceled | 已经被取消 |
| Unfinished | 这个并不属于WorkItem本身的状态，只是为了方便进行查询，他指Waiting或者Working状态 |
| NotCanceled | 这个并不属于WorkItem本身的状态，只是为了方便进行查询，未被取消的状态，指Waiting、Working或者Finished状态 |
| Unspecified | 未指定的状态，这个主要是为了方便查询 |