---
title: "WorkflowInstanceState"
source: "https://help.h3yun.com/contents/687/748.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance / WorkflowInstanceState"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkflowInstanceState
说明 : 流程实例的状态 
成员 : 

| 名称 | 说明 |
| --- | --- |
| Initiated | 初始化完成 |
| Starting | 正在启动 |
| Running | 正在运行 |
| Finishing | 正在结束 |
| Finished | 已完成 |
| Canceled | 已取消 |
| Unfinished | Finished和Cancel以外的所有状态 |
| NotCanceled | Cancel以外的状态 |
| Unspecified | 没有指定的状态，指所有状态 |