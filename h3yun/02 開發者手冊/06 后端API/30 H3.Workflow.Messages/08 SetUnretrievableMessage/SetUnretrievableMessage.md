---
title: "SetUnretrievableMessage"
source: "https://help.h3yun.com/contents/745/599.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / SetUnretrievableMessage"
updated: 2025-12-16
tags:
  - h3yun
  - 開發者手冊
---
类名 : SetUnretrievableMessage
说明 : 设置Token不可取回 
构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程ID |
| "activityCode" | 活动编码 |
| "tokenId" | 令牌的Id，这个ID必须与活动等待的ID匹配。这个值相当于一个KEY，用于匹配发送的消息是否与当前活动要等待的消息是一致的。只要一致的消息，才能被接受；否则消息会被丢掉。 |
| 返回值 |  |
| |
 |