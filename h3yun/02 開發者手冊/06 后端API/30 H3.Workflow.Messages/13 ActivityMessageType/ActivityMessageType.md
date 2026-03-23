---
title: "ActivityMessageType"
source: "https://help.h3yun.com/contents/750/618.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / ActivityMessageType"
updated: 2025-12-19
tags:
  - h3yun
  - 開發者手冊
---
类名 : ActivityMessageType
说明 : 发送给活动的消息类型 
成员 : 

| 名称 | 说明 |
| --- | --- |
| ActivateActivity | 激活活动 |
| AsyncEnd | 异步结束 |
| Cancel | 取消 |
| Rollback | 回滚，回滚并不是打回，打回用的激活活动的消息 |
| AdjustParticipant | 调整活动参与者，比如：活动参与者原来是A和B，通过该消息可以调整为B、C、D |
| SetUnretrievable | 设置Token不允许取回 |