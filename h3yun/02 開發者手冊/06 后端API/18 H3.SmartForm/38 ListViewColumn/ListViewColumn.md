---
title: "ListViewColumn"
source: "https://help.h3yun.com/contents/598/679.html"
category: "開發者手冊 / 后端API / H3.SmartForm / ListViewColumn"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : ListViewColumn
说明 : 列表的列信息 属性 : 

| 名称 | 说明 |
| --- | --- |
| Code | 编码 |
| DisplayName | 显示名称 |
| Visible | 是否可见 |
| Sortable | 是否排序 |
| Url | 连接:当前列的连接，参数值的传递方法{Code},可以是其他列的Code |
| Align | 对齐方式 |
| IsChild | 该列是否是子列 |
| IsLabel | 是否标签 |
| ChildColumns | 该列包含的子列 |
| ShowMode | 字段显示模式（数字控件千分位分隔符） |



构造方法名称 : #ctor(System.String,System.String,System.Boolean,System.Boolean,System.String,System.String,System.Boolean,H3.DataModel.PropertyShowMode)

| 参数 | 说明 |
| --- | --- |
| "code" | 列对应的字段的编码 |
| "displayName" | 列对应的显示名称 |
| "visible" | 该列是否可见 |
| "sortable" | 该列是否可排序 |
| "url" | 该列对应的Url链接 |
| "align" | 该列的排序方法 |
| "isLabel" | 是否标签 |
| "showMode" | 控件显示模式(千分位等) |
| 返回值 |  |
| |
 |