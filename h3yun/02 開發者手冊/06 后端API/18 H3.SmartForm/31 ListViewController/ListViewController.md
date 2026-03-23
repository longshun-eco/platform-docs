---
title: "ListViewController"
source: "https://help.h3yun.com/contents/591/647.html"
category: "開發者手冊 / 后端API / H3.SmartForm / ListViewController"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : ListViewController
说明 : 列表控制器，用于控制列表的提交和展示 属性 : 

| 名称 | 说明 |
| --- | --- |
| Request | 请求的上下文 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| ListViewControllerPostfix | 列表视图控制器的后缀 |
| Action\_LoadListViewSetting | 加载列表设置的操作名称 |
| Action\_Remove | 删除列表记录的操作名称 |
| ActivityName\_Name | 节点名称的表头编码 |
| ActivityName\_DisplayName | 节点名称的表头显示名称 |
| Status\_DisplayName | 流程状态的显示名称 |
| Participant\_DisplayName | 当前处理人 |
| Action\_Create | 创建 |
| Action\_Import | 导入 |
| Action\_Export | 导出 |
| Action\_PrintQrCode | 打印二维码 |
| Param\_ScopeType | 过滤条件 |
| Param\_Status | 数据状态 |
| Param\_ChildSchemaCode | 子表编码 |
| Param\_PagedByApplist | 根据applist分页 |
| Param\_IsDesignMode | 是否设计时 |
| Param\_ListViewDisplayMode | 显示模式 |


构造方法名称 : #ctor(H3.SmartForm.ListViewRequest)

| 参数 | 说明 |
| --- | --- |
| "request" | 请求的上下文 |
| 返回值 |  |
| |  |


方法名称 : OnAction(System.String,System.Object,H3.Workflow.Instance.WorkflowInstanceState,H3.Workflow.Instance.WorkflowInstanceState)

| 参数 | 说明 |
| --- | --- |
| "actionName" | 操作的名称 |
| "postValue" | 请求回传回来的数据 |
| "oldState" | |
| "newState" | |
| 返回值 |  |
| 响应的上下文 |  |


方法名称 : OnInit(H3.SmartForm.LoadListViewResponse)

| 参数 | 说明 |
| --- | --- |
| "response" | |
| 返回值 |  |
| |  |


方法名称 : InitActions(H3.SmartForm.LoadListViewResponse)

| 参数 | 说明 |
| --- | --- |
| "response" | |
| 返回值 |  |
| |  |


方法名称 : InitHeaders(H3.SmartForm.LoadListViewResponse)

| 参数 | 说明 |
| --- | --- |
| "response" | |
| 返回值 |  |
| |  |


方法名称 : LoadData(H3.SmartForm.LoadListViewResponse,H3.Data.Filter.Filter,System.Boolean,H3.DataModel.GetListScopeType,System.String,System.Boolean,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "response" | |
| "filter" | |
| "requireAssociatedBoHeaders" | |
| "listScopeType" | |
| "childSchemaCode" | |
| "pagedByParent" | |
| "isDesignMode" | |
| 返回值 |  |
| |  |


方法名称 : OnLoad(H3.SmartForm.LoadListViewResponse)

| 参数 | 说明 |
| --- | --- |
| "response" | |
| 返回值 |  |
| |  |


方法名称 : Submit(System.String,H3.SmartForm.ListViewPostValue)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Remove(H3.SmartForm.ListViewPostValue,H3.SmartForm.SubmitListViewResponse)

| 参数 | 说明 |
| --- | --- |
| "postValue" | |
| "response" | |
| 返回值 |  |
| |  |


方法名称 : OnSubmit(System.String,H3.SmartForm.ListViewPostValue,H3.SmartForm.SubmitListViewResponse)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |
 |