---
title: "IViewManager"
source: "https://help.h3yun.com/contents/625/812.html"
category: "開發者手冊 / 后端API / H3.SmartForm / IViewManager"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : IViewManager
说明 : 表单对象管理接口 
方法名称 : GetDraftForm(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | 表单编码 |
| 返回值 |  |
| 表单设置信息 |  |


方法名称 : GetPublishedForm(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | 表单编码 |
| 返回值 |  |
| 表单设置信息 |  |


方法名称 : GetPublishedForms(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "codes" | 表单编码集合 |
| 返回值 |  |
| 表单设置信息集合 |  |


方法名称 : GetBehindCodesByAppCode(System.String,System.DateTime@)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用编码 |
| "lastModifiedTime" | 整个应用中源代码的最后一次变更时间 |
| 返回值 |  |
| 应用的所有源代码 |  |


方法名称 : UpdateForm(H3.SmartForm.FormSetting)

| 参数 | 说明 |
| --- | --- |
| "form" | 表单对象 |
| 返回值 |  |
| 返回操作是否成功 |  |


方法名称 : PublishForm(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 表单编码 |
| 返回值 |  |
| 如果发布成功，则返回true，否则返回false |  |


方法名称 : AddListView(H3.SmartForm.ListViewSetting)

| 参数 | 说明 |
| --- | --- |
| "listView" | 查询对象 |
| 返回值 |  |
| 返回操作是否成功 |  |


方法名称 : UpdateDraftListView(H3.SmartForm.ListViewSetting)

| 参数 | 说明 |
| --- | --- |
| "listView" | 查询对象 |
| 返回值 |  |
| 返回操作是否成功 |  |


方法名称 : GetDraftListView(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | 查询编码 |
| 返回值 |  |
| 查询对象 |  |


方法名称 : GetPublishedListView(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | |
| 返回值 |  |
| |
 |