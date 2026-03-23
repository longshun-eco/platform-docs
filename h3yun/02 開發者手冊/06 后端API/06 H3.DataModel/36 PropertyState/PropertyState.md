---
title: "PropertyState"
source: "https://help.h3yun.com/contents/375/399.html"
category: "開發者手冊 / 后端API / H3.DataModel / PropertyState"
updated: 2025-12-21
tags:
  - h3yun
  - 開發者手冊
---
类名 : PropertyState
说明 : 业务对象的字段状态 属性 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName | 数据项名称 |
| DisplayName | 显示名称 |
| ChildSchemaCode | 子对象编码 |
| ChildView | 子视图 |
| ChildPropertyStates | 子对象字段 |
| Visible | 是否可见 |
| Editable | 是否可编辑 |
| Required | 要求必填 |
| Printable | 是否可打印 |



构造方法名称 : #ctor(System.String,System.String,System.Boolean,System.Boolean,System.Boolean,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 字段名称 |
| "displayName" | 显示名称 |
| "visible" | 是否可见 |
| "editable" | 是否可编辑 |
| "required" | 是否必填 |
| "printable" | 是否打印 |
| 返回值 |  |
| |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlDocument" | Xml文档 |
| "xmlElement" | Xml元素 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlElement" | xml元素 |
| 返回值 |  |
| |  |


方法名称 : Create(System.String,H3.DataModel.PropertySchema)

| 参数 | 说明 |
| --- | --- |
| "viewName" | 视图名称 |
| "propertySchema" | 字段名称 |
| 返回值 |  |
| 新建的默认的字段状态 |  |