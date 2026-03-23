---
title: "FunctionHelper"
source: "https://help.h3yun.com/contents/444/635.html"
category: "開發者手冊 / 后端API / H3.DataModel.Script / FunctionHelper"
updated: 2025-12-17
tags:
  - h3yun
  - 開發者手冊
---
类名 : FunctionHelper
说明 : 函数说明 属性 : 

| 名称 | 说明 |
| --- | --- |
| DisplayName | 显示名称 |
| Name | 函数名 |
| FunctionScenarioTypes | 函数使用场景 |
| FunctionCategories | 函数所属分类 |
| Example | 示例 |
| Description | 描述 |



构造方法名称 : #ctor(System.String,H3.DataModel.Script.FunctionCategory\[\],H3.DataModel.Script.FunctionScenarioType\[\],System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "name" | 函数名 |
| "functionCategories" | 函数分类 |
| "functionScenarioTypes" | 函数场景 |
| "description" | 函数描述 |
| "example" | 示例 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,H3.DataModel.Script.FunctionCategory\[\],H3.DataModel.Script.FunctionScenarioType\[\],System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "name" | 函数名 |
| "displayName" | 显示名称 |
| "functionCategories" | 分类 |
| "functionScenarioTypes" | 场景 |
| "description" | 描述 |
| "example" | 示例 |
| 返回值 |  |
| |  |


方法名称 : SupportCategory(H3.DataModel.Script.FunctionScenarioType,H3.DataModel.Script.FunctionCategory)

| 参数 | 说明 |
| --- | --- |
| "type" | 场景 |
| "category" | 分类 |
| 返回值 |  |
| 如果支持则返回true，否则返回false |  |


方法名称 : SupportScenario(H3.DataModel.Script.FunctionScenarioType)

| 参数 | 说明 |
| --- | --- |
| "type" | 场景 |
| 返回值 |  |
| 如果支持返回true,否则返回false |  |