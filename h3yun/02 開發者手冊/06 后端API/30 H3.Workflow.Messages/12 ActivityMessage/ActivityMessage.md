---
title: "ActivityMessage"
source: "https://help.h3yun.com/contents/749/616.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / ActivityMessage"
updated: 2025-12-14
tags:
  - h3yun
  - 開發者手冊
---
类名 : ActivityMessage
说明 : 发送给活动的消息的基类 属性 : 

| 名称 | 说明 |
| --- | --- |
| ActivityCode | 获取活动的编码 |
| TokenId | 获取或设置当前活动的Id |
| ActivityMessageType | 获取活动消息的类型 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.Int32,H3.Workflow.Messages.ActivityMessageType)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 目标流程实例的Id |
| "activityCode" | 活动编码 |
| "tokenId" | 当前活动ID |
| "activityMessageType" | 要发送给活动的消息的类型 |
| 返回值 |  |
| |  |


方法名称 : ToString

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |
 |