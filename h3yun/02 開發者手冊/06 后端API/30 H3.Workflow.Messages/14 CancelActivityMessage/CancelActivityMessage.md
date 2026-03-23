---
title: "CancelActivityMessage"
source: "https://help.h3yun.com/contents/751/634.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / CancelActivityMessage"
updated: 2025-12-14
tags:
  - h3yun
  - 開發者手冊
---
类名 : CancelActivityMessage
说明 : 发送给活动，取消该活动 属性 : 

| 名称 | 说明 |
| --- | --- |
| Rollback | 标记该取消消息是否是回滚消息，如果是回滚消息的话，那么流程会回滚当前状态到上一个步骤中，否则仅仅是取消该活动 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例的ID |
| "activityCode" | 活动名称 |
| "rollback" | 标记该取消消息是否是回滚消息，如果是回滚消息的话，那么流程会回滚当前状态到上一个步骤中，否则仅仅是取消该活动 |
| 返回值 |  |