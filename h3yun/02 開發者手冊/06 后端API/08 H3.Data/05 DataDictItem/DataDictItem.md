---
title: "DataDictItem"
source: "https://help.h3yun.com/contents/451/665.html"
category: "開發者手冊 / 后端API / H3.Data / DataDictItem"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : DataDictItem
说明 : 数据字典数据项 属性 : 

| 名称 | 说明 |
| --- | --- |
| ItemName | 数据名称 |
| IsArray | 数据的值是否是数组类型的 |
| ItemValue | 值，如果是数组，则用;隔开 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| StartTag | 变量前缀 |
| EndTag | 变量后缀 |
| TableName | 表名称 |
| PropertyName\_ItemName | 属性名称 |
| PropertyName\_IsArray | 属性名称 |
| PropertyName\_ItemValue | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.Boolean,System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 数据的名称 |
| "isArray" | |
| "value" | 数据的值 |
| 返回值 |  |
| |  |


方法名称 : GetValue

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 取到的值 |  |


方法名称 : GetKeyNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 键集合 |  |


方法名称 : GetKeyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "keyName" | 键 |
| 返回值 |  |
| 值 |  |


方法名称 : FindVariable(System.String,System.Int32,System.String@,System.Int32@,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "text" | 要匹配的文本 |
| "from" | 开始索引 |
| "word" | 搜索到的变量名称 |
| "startIndex" | 搜索到的变量的开始索引 |
| "endIndex" | 搜索到的变量的结束索引 |
| 返回值 |  |
| 如果找到变量则返回true，否则返回false |  |


方法名称 : FindVariables(System.String)

| 参数 | 说明 |
| --- | --- |
| "text" | 文本 |
| 返回值 |  |
| 所有的变量 |  |