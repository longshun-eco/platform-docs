---
title: "IReportManager"
source: "https://help.h3yun.com/contents/549/469.html"
category: "開發者手冊 / 后端API / H3.Reporting / IReportManager"
updated: 2025-12-21
tags:
  - h3yun
  - 開發者手冊
---
类名 : IReportManager
说明 : BPA服务接口 
方法名称 : AddReportPage(H3.Reporting.ReportPage)

| 参数 | 说明 |
| --- | --- |
| "reportPage" | 报表页 |
| 返回值 |  |
| |  |


方法名称 : RemoveReportPage(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | 报表页编码 |
| 返回值 |  |
| |  |


方法名称 : UpdateReportPage(H3.Reporting.ReportPage)

| 参数 | 说明 |
| --- | --- |
| "reportPage" | 报表页 |
| 返回值 |  |
| |  |


方法名称 : GetReportPage(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | 报表页编码 |
| 返回值 |  |
| |  |


方法名称 : GetReportWidget(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "reportWidgetId" | 报表配置Id |
| "reportPageCode" | 报表页编码 |
| 返回值 |  |
| |  |


方法名称 : GetReportWidgetSimpleBoard(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "simpleBoardId" | 单个看板格Id |
| "reportWidgetId" | 报表配置Id |
| "reportPageCode" | 报表页Id |
| 返回值 |  |
| |  |


方法名称 : GetReportSource(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "sourceId" | 数据源Id |
| "reportPageCode" | 报表页Id |
| 返回值 |  |
| |  |


方法名称 : GetReportWidgetAndOtherInfo(System.String,System.String,System.String@,System.Int32@,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "reportWidgetId" | 报表页Id |
| "reportPageID" | 报表Id |
| "reportPageCode" | 报表编码 |
| "reportWidgetIndex" | 报表页位置 |
| "reportWidgetTotal" | 报表页总数 |
| 返回值 |  |