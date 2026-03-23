---
title: "IDataDictManager"
source: "https://help.h3yun.com/contents/452/669.html"
category: "開發者手冊 / 后端API / H3.Data / IDataDictManager"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : IDataDictManager
说明 : 数据字典接口 
方法名称 : ExistsItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 项目名称 |
| 返回值 |  |
| 返回是否存在 |  |


方法名称 : CreateItem(System.String,System.Boolean,System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 变量名称 |
| "isArray" | 是否是数组 |
| "itemValue" | 变量值 |
| 返回值 |  |
| 如果成功，则返回0，否则返回错误代码 H3.ErrorCode |  |


方法名称 : GetItemValue(System.String,System.Type)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 数据字典名称 |
| "type" | 值得类型 |
| 返回值 |  |
| 数据字典值 |  |


方法名称 : UpdateItem(System.String,System.Boolean,System.String)

| 参数 | 说明 |
| --- | --- |
| "isArray" | 是否数组 |
| "itemName" | 数据字典名称 |
| "itemValue" | 数据字典值 |
| 返回值 |  |
| 如果成功，则返回0，否则返回错误代码 H3.ErrorCode |  |


方法名称 : GetAllItems

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 数据字典数据项集合 |  |


方法名称 : SearchItems(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "searchName" | |
| "searchValue" | |
| 返回值 |  |
| |  |


方法名称 : GetAllItemsName

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 数据字典数据项名称集合 |  |


方法名称 : RemoveItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 数据字典名称 |
| 返回值 |  |
| |  |


方法名称 : GetItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 数据字典名称 |
| 返回值 |  |
| 数据字典 |  |


方法名称 : GetItems(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "itemNames" | 名称数组 |
| 返回值 |  |
| 多个数据字典 |  |