---
title: "ReturnColumn"
source: "https://help.h3yun.com/contents/455/681.html"
category: "開發者手冊 / 后端API / H3.Data.Filter / ReturnColumn"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : ReturnColumn
说明 : 要返回的列的设置 属性 : 

| 名称 | 说明 |
| --- | --- |
| ColumnName | 列名称，这里不包含表名 |
| Alias | 列别名 |
| Function | 函数名 |



构造方法名称 : #ctor(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "columnName" | 列名 |
| "alias" | 别名 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Data.Filter.SQLFunction,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "function" | 函数名 |
| "columnName" | 列名 |
| "alias" | 别名 |
| 返回值 |  |
| |  |


方法名称 : ToString

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 列的名称 |  |