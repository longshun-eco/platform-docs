---
title: "AdjustParticipantMessage"
source: "https://help.h3yun.com/contents/746/604.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / AdjustParticipantMessage"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : AdjustParticipantMessage
说明 : 调整活动参与者的消息。比如：原来活动的参与者是A、B，我们可以发送一个消息将参与者调整为B、C、D，那么引擎会自动取消掉A的任务，同时，创建C和D的任务 属性 : 

| 名称 | 说明 |
| --- | --- |
| Participants | 新的活动参与者。比如：原来活动的参与者是A、B，我们可以发送一个消息将参与者调整为B、C、D，那么该参数的值是B、C和D |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例的Id |
| "activityCode" | 活动编码 |
| "participants" | 新的活动参与者。比如：原来活动的参与者是A、B，我们可以发送一个消息将参与者调整为B、C、D，那么该参数的值是B、C和D |
| 返回值 |  |
| |
 |