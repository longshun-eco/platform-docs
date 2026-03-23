---
title: "ItemMatcher"
source: "https://help.h3yun.com/contents/459/689.html"
category: "開發者手冊 / 后端API / H3.Data.Filter / ItemMatcher"
updated: 2025-12-17
tags:
  - h3yun
  - 開發者手冊
---
类名 : ItemMatcher
说明 : 属性匹配器 属性 : 

| 名称 | 说明 |
| --- | --- |
| ItemName | 要匹配的项目的名称 |
| ComparisonOperator | 匹配的比较符号 |
| Value | 目标值 |
| IsColumn | ItemValue是否是列 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| Tag\_Name | 属性名称 |
| Tag\_Value | 属性名称 |


构造方法名称 : #ctor(System.String,H3.Data.ComparisonOperatorType,System.Object,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "itemName" | 要匹配的项目的名称 |
| "comparisonOperator" | 匹配的比较符号 |
| "value" | 目标值 |
| "isColumn" | 是否是列 |
| 返回值 |  |
| |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlDocument" | xml文档 |
| "xmlElement" | xml元素 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlElement" | xml元素 |
| 返回值 |  |