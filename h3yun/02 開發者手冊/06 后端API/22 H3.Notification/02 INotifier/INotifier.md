---
title: "INotifier"
source: "https://help.h3yun.com/contents/664/741.html"
category: "開發者手冊 / 后端API / H3.Notification / INotifier"
updated: 2025-12-15
tags:
  - h3yun
  - 開發者手冊
---
类名 : INotifier
说明 : 用于管理通知的接口 
方法名称 : Notify(H3.Notification.Notification)

| 参数 | 说明 |
| --- | --- |
| "notification" | 要发送的通知 |
| 返回值 |  |
| |  |


方法名称 : Send(H3.Notification.UserMessage\[\])

| 参数 | 说明 |
| --- | --- |
| "messages" | 要发送的消息 |
| 返回值 |  |
| |  |


方法名称 : SetState(System.String,H3.Notification.UserMessageState)

| 参数 | 说明 |
| --- | --- |
| "messageId" | 用户消息的Id |
| "state" | 新的状态 |
| 返回值 |  |