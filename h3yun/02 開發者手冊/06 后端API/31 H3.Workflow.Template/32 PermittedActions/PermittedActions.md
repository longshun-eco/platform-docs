---
title: "PermittedActions"
source: "https://help.h3yun.com/contents/736/566.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / PermittedActions"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : PermittedActions
说明 : 许可的动作 属性 : 

| 名称 | 说明 |
| --- | --- |
| Flag | 标志位 |
| Forward | 是否可以转发 |
| Consult | 是否可以征询意见 |
| Backward | 是否可以反向流转 |
| Choose | 是否可以手工选择 |
| Jump | 是否可以跳转 |
| RejectToStart | 返回到开始节点 |
| Reject | 是否允许打回 |
| RejectToAny | 是否允许驳回到之前的任何一个活动 |
| RejectToFixed | 是否允许驳回到指定的活动 |
| SubmitToRejectedActivity | 是否允许提交到驳回前的活动 |
| RejectToActivityCodes | 允许驳回到的活动 |
| CancelIfUnfinished | 在工作项提交前，是否可以取消流程 |
| CancelIfFinished | 在工作项提交后，是否可以取消流程 |
| Retrieve | 是否可以取回 |
| Cancel | 是否可以取消活动 |
| Suspend | 是否可以挂起流程 |
| ViewInstanceState | 是否可以查看流程图 |
| AdjustParticipant | 是否可以调整活动参与者 |
| Circulate | 是否可以传阅 |
| Recirculate | 是否可以再传阅 |
| ViewData | 是否可以查看流程数据 |
| Assist | 是否可以协助 |
| FinishInstance | 是否可以直接结束流程 |
| PreviewParticipant | 是否可以预览后面活动的参与者 |
| DefaultPermittedActions | 默认的权限 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| FORWARD\_MASK | 是否允许转发 |
| CONSULT\_MASK | 是否允许征询意见 |
| BACKWARD\_MASK | 是否允许反向流转 |
| CHOOSE\_MASK | 是否允许手工选择 |
| JUMP\_MASK | 是否允许跳转 |
| CANCELIFUNFINISHED\_MASK | 是否允许用户有待办任务的条件下取消流程 |
| RETRIEVE\_MASK | 是否允许取回 |
| CANCEL\_MASK | 是否允许取消工作项 |
| SUSPEND\_MASK | 是否允许挂起 |
| VIEWINSTANCESTATE\_MASK | 是否允许查看流程状态 |
| ADJUST\_PARTICIPANT\_MASK | 是否允许调整活动参与者 |
| REJECTTOSTART\_MASK | 是否允许打回到发起节点 |
| CIRCULATE\_MASK | 是否允许传阅 |
| REJECT\_MASK | 是否允许打回 |
| CANCELIFFINISHED\_MASK | 提交之后是否允许取消流程 |
| VIEWDATA\_MASK | 查看流程数据 |
| REJECTTOANY\_MASK | 驳回到前面任何一个活动 |
| ASSIST\_MASK | 协助 |
| RECIRCULATE\_MASK | 再传阅 |
| FINISHINSTANCE\_MASK | 直接结束流程 |
| PREVIEWPARTICIPANT\_MASK | 预览后续的参与者 |
| REJECTTOFIXED\_MASK | 驳回到指定的活动 |
| SUBMITTOREJECTEDACTIVITY\_MASK | 是否允许提交到驳回前的活动 |
| DefaultFlag | 无动作 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Int64)

| 参数 | 说明 |
| --- | --- |
| "flag" | 标志位，用于记录所有的许可条件 |
| 返回值 |  |
| |  |


方法名称 : CreateDefault

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "XmlDocument" | |
| "XmlElement" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "XmlElement" | |
| 返回值 |  |
| |
 |