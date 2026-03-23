---
title: "TokenState"
source: "https://help.h3yun.com/contents/693/770.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance / TokenState"
updated: 2025-12-15
tags:
  - h3yun
  - 開發者手冊
---
类名 : TokenState
说明 : 令牌的状态 
成员 : 

| 名称 | 说明 |
| --- | --- |
| Running | 运行状态 |
| Finished | 完成状态 |
| Dropped | 被取消掉了的状态，当发生了Rollback或者取消后，相应的Token将会被废弃 |
| Unspecified | 所有状态，用于查询 |
| Undropped | 未被取消的状态，用于查询 |