---
title: "LoadSmartFormResponse"
source: "https://help.h3yun.com/contents/608/712.html"
category: "開發者手冊 / 后端API / H3.SmartForm / LoadSmartFormResponse"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : LoadSmartFormResponse
说明 : 加载表单的时候，表单返回到前台的数据 属性 : 

| 名称 | 说明 |
| --- | --- |
| WorkflowState | 流程状态 |
| ActivityCode | 获取或设置提交/驳回的节点名称 |
| DisplayName | 获取或设置表单的显示名称 |
| SchemaCode | 获取或设置数据模型显示名称 |
| Originator | 获取或设置发起人Id |
| OriginatorCode | 获取或设置发起人Code |
| OriginatorParentId | 获取或设置发起人所属父组织的Id |
| WorkflowVersion | 获取或设置流程版本号 |
| FormMode | 获取或设置当前表单模式 |
| IsCreateMode | 是否发起模式 |
| InstanceId | 获取或设置流程实例ID |
| BizObjectId | 业务对象ID |
| BizObjectStatus | 业务对象状态 |
| WorkItemId | 获取或设置工作任务Id |
| Close | 获取或设置消息通知后是否立即关闭窗口 |
| WorkItemType | 获取当前工作任务的类型 |
| Actions | 表单操作 |
| AssociatedBoNames | 与该表单关联的对象的Id与名称表 |
| AssociationLists | 与该表单关联的列表的SchemaCode与名称的表 |
| EnableFormSns | 启用表单动态 |
| EnableTask | 启用任务提醒 |
| Name | 表单名称 |
| FormDataType | 表单数据类型 |
| ReturnData | 返回给前端的数据集 |
| PrintConfig | 打印配置信息，用于标记"公司名称","审批"等信息是否打印 |
| Comments | 如果表单是流程表单，则该字段有效，用于显示该流程的所有审批记录 |
| WorkItems | 返回流程的所有工作任务信息 |
| RequestParameters | 由H3系统使用，用来控制整个表单的上下文变量 |
| QrCodeUrl | 二维码地址 |



方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | |
| 返回值 |  |
| |  |


方法名称 : GetBizObjectArrayData(System.String)

| 参数 | 说明 |
| --- | --- |
| "dataFiled" | |
| 返回值 |  |
| |  |


方法名称 : GetBizObjectArrayTemplate(System.String)

| 参数 | 说明 |
| --- | --- |
| "dataFiled" | |
| 返回值 |  |
| |  |