---
title: "IAppPackageManager"
source: "https://help.h3yun.com/contents/321/325.html"
category: "開發者手冊 / 后端API / H3.App / IAppPackageManager"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : IAppPackageManager
说明 : 应用包管理器，在这里对一个应用下面的所有对象进行统一的添加、删除和发布 
方法名称 : AddApp(H3.App.AppHeader)

| 参数 | 说明 |
| --- | --- |
| "appHeader" | 应用头信息 |
| 返回值 |  |
| 如果添加成功则返回Success，否则返回错误代码 |  |


方法名称 : GetAppHeader(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用的编码 |
| 返回值 |  |
| 应用头信息 |  |


方法名称 : GetAppHeaders

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 系统中所有的应用 |  |


方法名称 : UpdateAppHeader(H3.App.AppHeader)

| 参数 | 说明 |
| --- | --- |
| "appHeader" | 应用头 |
| 返回值 |  |
| 如果更新成功，则返回true，否则返回false |  |


方法名称 : AddModule(H3.App.FunctionNode)

| 参数 | 说明 |
| --- | --- |
| "functionNode" | 表单模块对应的功能节点的设置 |
| 返回值 |  |
| 如果添加成功则返回true，否则返回false。通常添加失败是由于记录或者编码已经存在 |  |


方法名称 : GetFunctionNodes

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 所有菜单节点 |  |


方法名称 : GetNodeSummaryTree(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | 根节点Code |
| 返回值 |  |
| |  |


方法名称 : GetFunctionNode(System.String)

| 参数 | 说明 |
| --- | --- |
| "functionCode" | 菜单节点编码 |
| 返回值 |  |
| 返回菜单节点对象 |  |


方法名称 : GetFunctionNodesByAppCode(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用编码 |
| 返回值 |  |
| 返回子菜单节点集合 |  |


方法名称 : GetFunctionNodesByParentCode(System.String)

| 参数 | 说明 |
| --- | --- |
| "parentCode" | 父节点编码 |
| 返回值 |  |
| 返回子菜单节点集合 |  |


方法名称 : RemoveFunctionNode(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | 节点编码 |
| 返回值 |  |
| 返回节点移除是否成功 |  |


方法名称 : AddFunctionNode(H3.App.FunctionNode)

| 参数 | 说明 |
| --- | --- |
| "node" | 功能节点对象 |
| 返回值 |  |
| 返回添加是否成功 |  |


方法名称 : UpdateFunctionNode(H3.App.FunctionNode)

| 参数 | 说明 |
| --- | --- |
| "node" | 功能节点对象 |
| 返回值 |  |
| 返回更新是否成功 |  |


方法名称 : UpdateFunctionNodes(H3.App.FunctionNode\[\])

| 参数 | 说明 |
| --- | --- |
| "nodes" | 要更新的节点 |
| 返回值 |  |
| 返回更新是否成功 |  |


方法名称 : GetFunctionNodesByNodeType(H3.App.FunctionNodeType)

| 参数 | 说明 |
| --- | --- |
| "nodeType" | 节点类型 |
| 返回值 |  |
| 返回指定节点类型的集合 |  |


方法名称 : UpdateSortKeys(System.Collections.Generic.Dictionary{System.String,System.Int32})

| 参数 | 说明 |
| --- | --- |
| "sortKeys" | 菜单的次序表，格式是(菜单编码，次序序号) |
| 返回值 |  |
| |  |


方法名称 : UpdateDraft(H3.DataModel.BizObjectSchema,H3.SmartForm.FormSetting,H3.SmartForm.ListViewSetting)

| 参数 | 说明 |
| --- | --- |
| "schema" | 数据模型对象 |
| "form" | 表单对象 |
| "listView" | 列表视图对象 |
| 返回值 |  |
| 返回更新是否成功 |  |


方法名称 : PublishModule(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "moduleCode" | 模块编码 |
| "validateSchema" | 是否校验 |
| 返回值 |  |
| 如果发布成功则返回SUCCESS，否则返回错误代码 |  |


方法名称 : DeleteModule(System.String)

| 参数 | 说明 |
| --- | --- |
| "moduleCode" | 应用模块编码 |
| 返回值 |  |
| |  |


方法名称 : DeleteGroupModule(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | 应用模块编码 |
| 返回值 |  |
| |  |


方法名称 : DeleteApp(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 要删除的应用的编码 |
| 返回值 |  |
| |  |


方法名称 : RemoveSolution(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | |
| 返回值 |  |
| |  |


方法名称 : UpdateName(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | 要更新的应用或者应用模块的编码 |
| "displayName" | 更新后的显示名称 |
| 返回值 |  |
| |  |


方法名称 : AddAppSolution(H3.App.AppSolution)

| 参数 | 说明 |
| --- | --- |
| "appSolution" | 解决方案对象 |
| 返回值 |  |
| |  |


方法名称 : UpdateAppSolution(H3.App.AppSolution)

| 参数 | 说明 |
| --- | --- |
| "appSolution" | 解决方案对象 |
| 返回值 |  |
| |  |


方法名称 : RemoveAppSolution(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | 解决方案编码 |
| 返回值 |  |
| |  |


方法名称 : GetAppSolution(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | 解决方案编码 |
| 返回值 |  |
| |  |


方法名称 : GetAllAppSolutions

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetUninstalledAppSolutions

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |