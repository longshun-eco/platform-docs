---
title: "FunctionNode"
source: "https://help.h3yun.com/contents/318/322.html"
category: "開發者手冊 / 后端API / H3.App / FunctionNode"
updated: 2025-12-15
tags:
  - h3yun
  - 開發者手冊
---
类名 : FunctionNode
说明 : 功能节点 属性 : 

| 名称 | 说明 |
| --- | --- |
| Code | 节点编码(类型内唯一) |
| IsSystem | 是否是系统节点，如果是则无法删除 |
| State | 状态 |
| AppCode | 父节点编码 |
| ParentCode | 父节点编码 |
| IsWorkflowNode | 是否流程中心里的 流程表单节点 |
| DisplayName | 显示名称 |
| SortKey | 序号,高4位是流程包排序，高4位外是流程排序 |
| Visible | PC端是否在主菜单显示 |
| NodeVisible | 是否在主菜单显示 |
| NodeType | 树节点类型 |
| IconCss | 获取或设置图标的CSS名称 |
| Url | 页面链接 |
| EnableDataAcl | 启用数据权限 |
| DataAclInheritedFrom | 数据权限的继承自哪个对象 |
| Removable | 该菜单是否可以删除 |
| OpenType | 菜单在移动端的打开方式 |
| IsAppSetting | 是SaaS配置 |
| Valid | 验证是否合法 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| MaxCodeLength | 编码的最大长度 |
| MaxNameLength | 名称的最大长度 |
| PropertyName\_Code | 属性名称 |
| PropertyName\_IsSystem | 属性名称 |
| PropertyName\_State | 状态属性名称 |
| PropertyName\_AppCode | 属性名称 |
| PropertyName\_ParentCode | 属性名称 |
| PropertyName\_DisplayName | 属性名称 |
| PropertyName\_SortKey | 序号属性 |
| PropertyName\_Visible | 属性名称 |
| PropertyName\_NodeVisible | 属性名称 |
| PropertyName\_NodeType | 属性名称 |
| PropertyName\_IconCss | 图标CSS名称 |
| PropertyName\_Url | 属性名称 |
| PropertyName\_EnableDataAcl | 属性名称 |
| PropertyName\_DataAclInheritedFrom | 属性名称 |
| PropertyName\_Removable | 属性名称 |
| PropertyName\_OpenType | 属性名称 |
| PropertyName\_IsAppSetting | 属性名称 |
| App\_Workflow | 应用程序:流程中心 |
| App\_Workflow\_MyUnfinishedWordItem | 待办任务 |
| App\_Workflow\_MyFinishedWordItem | 已办任务 |
| App\_Workflow\_MyWorkflow | 发起流程 |
| App\_Workflow\_MyInstance | 我的流程 |
| App\_Workflow\_SearchIntance | 查询流程 |
| App\_Contacts | 通讯录 |
| App\_Contacts\_Child | 通讯录用于左侧菜单 |
| App\_Report | 应用程序:报表中心 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetKeyNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetKeyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "KeyName" | |
| 返回值 |  |
| |  |


方法名称 : CompareTo(H3.App.FunctionNode)

| 参数 | 说明 |
| --- | --- |
| "other" | |
| 返回值 |  |