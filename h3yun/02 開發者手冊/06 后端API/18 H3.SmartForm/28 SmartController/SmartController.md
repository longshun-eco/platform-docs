---
title: "SmartController"
source: "https://help.h3yun.com/contents/588/630.html"
category: "開發者手冊 / 后端API / H3.SmartForm / SmartController"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : SmartController
说明 : 表单控制器基类 属性 : 

| 名称 | 说明 |
| --- | --- |
| Engine | 引擎对象 |
| JavaScriptSerializer | 序列化、反序列化器 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| Action\_Load | 加载表单数据 |
| MethodName | 运行方法名称 |


构造方法名称 : #ctor(H3.SmartForm.RequestContext)

| 参数 | 说明 |
| --- | --- |
| "request" | 请求上下文 |
| 返回值 |  |
| |  |


方法名称 : RunAction(System.String,System.Object,H3.Workflow.Instance.WorkflowInstanceState,H3.Workflow.Instance.WorkflowInstanceState,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "actionName" | |
| "postValue" | |
| "oldState" | |
| "newState" | |
| "enableDebugger" | |
| 返回值 |  |
| |  |


方法名称 : OnAction(System.String,System.Object,H3.Workflow.Instance.WorkflowInstanceState,H3.Workflow.Instance.WorkflowInstanceState)

| 参数 | 说明 |
| --- | --- |
| "actionName" | |
| "postValue" | |
| "oldState" | |
| "newState" | |
| 返回值 |  |
| |  |


方法名称 : Deserialize\`\`1(System.String)

| 参数 | 说明 |
| --- | --- |
| "value" | |
| 返回值 |  |
| |  |


方法名称 : Serialize(System.Object)

| 参数 | 说明 |
| --- | --- |
| "value" | |
| 返回值 |  |
| |  |