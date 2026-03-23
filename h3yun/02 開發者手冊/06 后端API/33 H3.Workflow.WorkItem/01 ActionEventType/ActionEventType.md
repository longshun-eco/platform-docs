---
title: "ActionEventType"
source: "https://help.h3yun.com/contents/646/387.html"
category: "開發者手冊 / 后端API / H3.Workflow.WorkItem / ActionEventType"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : ActionEventType
说明 : 激活活动的类型 
成员 : 

| 名称 | 说明 |
| --- | --- |
| None | 用于WorkItem.PreActionEventType，表示前一个步骤既不是提交页不是打回，可能是直接激活了某个活动，或者是征询意见、协办之类的请求创建的任务 |
| Forward | 流程向下流转，通常是普通的提交事件 |
| Backward | 流程回退流转，通常是打回的时候激活 |
| Adjust | 调整活动激活 |