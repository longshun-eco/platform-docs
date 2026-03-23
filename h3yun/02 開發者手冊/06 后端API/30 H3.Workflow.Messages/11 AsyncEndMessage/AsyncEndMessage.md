---
title: "AsyncEndMessage"
source: "https://help.h3yun.com/contents/748/611.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / AsyncEndMessage"
updated: 2025-12-19
tags:
  - h3yun
  - 開發者手冊
---
类名 : AsyncEndMessage
说明 : 通知活动异步等待已经结束 属性 : 

| 名称 | 说明 |
| --- | --- |
| ContinuePostActivity | 如果接收方活动在处理完该消息后进入完成状态，那么该属性用于标记是否自动触发该活动后面的活动，如果为false，那么将不继续触发该活动后续的活动 |
| AttachedMessage | 如果接收方活动在处理完该消息后进入完成状态，同时，该属性不为空，那么该活动将发送出该消息 |
| ForceFinishing | 强制结束 |
| ForceApproval | 强制审批结果 |
| Approval | 用于记录处理后的结果，记录审批结果 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.Int32,H3.Data.BoolValue,System.Boolean,H3.Data.BoolValue,System.Boolean,H3.Workflow.Messages.Message)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例ID |
| "activityCode" | 活动节点编码 |
| "tokenId" | 当前活动ID |
| "approval" | 当前任务审批结果 |
| "forceFinishing" | 是否强制结束剩余任务 |
| "forceApproval" | 强制结束剩余任务时采用审核结果 |
| "continuePostActivity" | 是否继续激活后续活动 |
| "attachedMessage" | 附加继续执行消息 |
| 返回值 |  |
| |
 |