---
title: "ActivateActivityMessage"
source: "https://help.h3yun.com/contents/752/640.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / ActivateActivityMessage"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : ActivateActivityMessage
说明 : 发送给流程，通知该流程激活某一个活动 属性 : 

| 名称 | 说明 |
| --- | --- |
| CheckEntry | 是否检查入口条件 |
| Participants | 该活动的参与人 |
| PreTokens | 该活动前面的令牌 |
| PreActionEventType | 激活的活动的时候，用户在前面一个任务上的做的操作 |
| SkippedExecution | 用于记录处理后的结果，如果为true表示该活动实际上并没有执行，而是直接跳过了。比如：上一个步骤的审批人跟当前步骤的审批人是同一个人，那么这个步骤可能会被跳过；另外，对于连接点活动，也是执行跳过的 |
| Approval | 用于记录处理后的结果，记录审批结果 |
| FinishActivity | 直接结束掉这个节点 |
| DestActivityCode | 如果FinishActivity=true，那么该参数有效，用于指定当活动结束后，需要跳转的目标活动 |



构造方法名称 : #ctor(System.String,System.String,System.Int32,System.String\[\],System.Int32\[\],System.Boolean,H3.Workflow.WorkItem.ActionEventType)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例的ID |
| "activityCode" | 活动编码 |
| "tokenId" | 令牌ID，或者叫步骤ID，流程实例每走过一个活动该ID会自动加1。令牌与活动是N:1的关系 |
| "participants" | 参与者，激活活动后，会采用该参数的参与者来作为活动的参与者，而不会使用在流程活动中定义的参与者 |
| "preTokens" | 前驱令牌，当流程需要回滚的时候，会回滚给这些前驱 |
| "checkEntry" | 是否需要检查入口条件，如果不需要检查入口条件，则直接激活目标活动 |
| "preActionEventType" | 前面一个步骤的操作，可以是提交或者打回 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.Int32,System.String\[\],System.Int32\[\],System.Boolean,H3.Workflow.WorkItem.ActionEventType,System.Boolean,System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例的ID |
| "activityCode" | 活动编码 |
| "tokenId" | 令牌ID，或者叫步骤ID，流程实例每走过一个活动该ID会自动加1。令牌与活动是N:1的关系 |
| "participants" | 参与者，激活活动后，会采用该参数的参与者来作为活动的参与者，而不会使用在流程活动中定义的参与者 |
| "preTokens" | 前驱令牌，当流程需要回滚的时候，会回滚给这些前驱 |
| "checkEntry" | 是否需要检查入口条件，如果不需要检查入口条件，则直接激活目标活动 |
| "preActionEventType" | 前面一个步骤的操作，可以是提交或者打回 |
| "finishActivity" | 是否立即结束活动 |
| "destActivityCode" | 立即结束活动后需要激活的节点 |
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