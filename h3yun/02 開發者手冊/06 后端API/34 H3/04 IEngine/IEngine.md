---
title: "IEngine"
source: "https://help.h3yun.com/contents/534/370.html"
category: "開發者手冊 / 后端API / H3 / IEngine"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : IEngine
说明 : 引擎，通过该接口来访问服务 属性 : 

| 名称 | 说明 |
| --- | --- |
| EngineConfig | 引擎的基础配置 |
| SettingManager | 配置管理器 |
| WorkflowTemplateManager | 流程管理器 |
| BizBus | 集成服务 |
| BizObjectManager | 数据模型管理器 |
| BizObjectTrackManager | 业务对象变更日志管理器 |
| PrintTemplateManager | 套打模板管理器 |
| ViewManager | 表单管理器 |
| DataDictManager | 元数据管理器 |
| Notifier | 用于通知 |
| WorkflowInstanceManager | 流程实例管理器 |
| WorkItemManager | 工作项管理器 |
| AgencyManager | 委托管理器 |
| UrgencyManager | 催办 |
| TaskManager | 定时器 |
| Organization | 组织结构管理器 |
| FunctionAclManager | 功能权限控制器 |
| RecentObjectManager | 最近访问过的对象和应用 |
| AppPackageManager | 流程包 |
| AppMarketManager | 应用市场 |
| ReportManager | 分析器，用于分析报表 |
| Query | 查询器，用于直接查询数据库，这是一个特殊的属性，客户端调用Query的时候，并不通过Engine，而是直接访问数据库，所以在这里没有标记为服务器集群模块 |
| ReportQuery | 报表查询器 |
| SNSManager | 企业社交管理器 |
| IndexManager | 索引和搜索关键词的对象 |
| Interactor | 交互服务。外部系统与引擎交互，有的时候为了完成某一项工作，需要与引擎多次交互，为了提高这种交互效率，我们在这里将多个接口封装成一个接口，一次调用即可完成所有工作 |



方法名称 : GetEngineUsage(H3.Clusterware.Operation.EngineUsage@,System.Collections.Generic.Dictionary{System.String,H3.ServiceHub.Operation.EngineSolutionLicense}@)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 引擎的使用情况 |  |