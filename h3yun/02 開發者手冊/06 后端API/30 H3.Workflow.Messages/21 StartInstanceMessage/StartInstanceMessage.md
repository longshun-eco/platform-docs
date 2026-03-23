---
title: "StartInstanceMessage"
source: "https://help.h3yun.com/contents/758/660.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / StartInstanceMessage"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : StartInstanceMessage
说明 : 发送给流程，通知流程进行启动 属性 : 

| 名称 | 说明 |
| --- | --- |
| NotifyParentActivityFinished | 结束的时候是否通知父流程 |
| ParentActivityTokenId | 父流程活动的TokenId |
| FinishStartActivity | 获取是否要自动结束开始节点 |
| DestActivityCode | 获取当自动结束第一个活动时，需要跳转的目标活动 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例的Id |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.Boolean,System.String,System.Boolean,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例ID |
| "finishStartActivity" | 是否结束第一个活动 |
| "destActivityCode" | 结束第一个活动后提交的目标节点 |
| "notifyParentActivityFinished" | 是否通知父流程活动结束 |
| "parentActivityTokenId" | 父流程中活动节点TokenID |
| 返回值 |  |
| |
 |