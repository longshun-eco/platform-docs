---
title: "ActivityFinishedMessage"
source: "https://help.h3yun.com/contents/753/645.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / ActivityFinishedMessage"
updated: 2025-12-17
tags:
  - h3yun
  - 開發者手冊
---
类名 : ActivityFinishedMessage
说明 : 发送给流程，通知流程某个活动已经完成 属性 : 

| 名称 | 说明 |
| --- | --- |
| ActivityCode | 活动编码 |
| TokenId | 使用的令牌 |
| ContinueRoute | 完成后是否还继续流转，如果继续流转，那么将自动激活后面的活动，否则只是结束本活动，不自动激活后续的活动。通常，我们在手动调整活动的时候，会设置该参数为false，那么系统不会自动往下流转 |
| DestActivityCode | 获取在自动结束活动时，需要调整的活动节点编码 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.Int32,System.Boolean,System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例的ID |
| "activityCode" | 活动编码 |
| "tokenId" | 令牌ID，或者叫步骤ID，流程实例每走过一个活动该ID会自动加1。令牌与活动是N:1的关系 |
| "continueRoute" | 完成后是否还继续流转，如果继续流转，那么将自动激活后面的活动，否则只是结束本活动，不自动激活后续的活动。通常，我们在手动调整活动的时候，会设置该参数为false，那么系统不会自动往下流转 |
| "destActivityCode" | 活动自动完成时，下一活动节点编码 |
| 返回值 |  |
| |
 |