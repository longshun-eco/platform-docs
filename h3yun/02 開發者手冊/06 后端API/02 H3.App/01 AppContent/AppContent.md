---
title: "AppContent"
source: "https://help.h3yun.com/contents/305/304.html"
category: "開發者手冊 / 后端API / H3.App / AppContent"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : AppContent
说明 : 一款应用的全部内容，包括表单、工作流等 属性 : 

| 名称 | 说明 |
| --- | --- |
| IsWorkflow | 当前应用是否是流程模板 |
| AppHeader | 应用头信息，用于记录应用的名称之类的 |
| Modules | 每个模块的信息 |
| DataDictItems | 该应用使用到的数据字典 |
| CheckAccessPoint | 安装该应用的时候，是否需要检查连接点 |



方法名称 : CreateXml(H3.Data.IDataDictManager)

| 参数 | 说明 |
| --- | --- |
| "dataDictManager" | 数据字典，因为可能需要打包对应的数据字典，所以需要传入该字段 |
| 返回值 |  |
| 应用打包成的XML |  |


方法名称 : Parse(System.String)

| 参数 | 说明 |
| --- | --- |
| "xml" | Xml格式的应用内容 |
| 返回值 |  |
| 应用 |  |