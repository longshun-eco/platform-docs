---
title: "PropertyPermission"
source: "https://help.h3yun.com/contents/729/543.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / PropertyPermission"
updated: 2025-12-18
tags:
  - h3yun
  - 開發者手冊
---
类名 : PropertyPermission
说明 : 数据权限对象 属性 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName | 数据项名称 |
| Visible | 是否可见 |
| Editable | 是否可编辑 |
| TrackVisible | 是否可以看见数据修改痕迹 |
| Required | 要求必输 |
| Printable | 是否打印 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.Boolean,System.Boolean,System.Boolean,System.Boolean,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 项名称 |
| "visible" | 数据项是否可见 |
| "editable" | 数据项是否可以编辑 |
| "trackVisible" | 数据变更日志是否可见 |
| "required" | 是否必填 |
| "printable" | 是否打印 |
| 返回值 |  |
| |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "XmlDocument" | |
| "XmlElement" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "XmlElement" | |
| 返回值 |  |
| |  |


方法名称 : CreateDefaultPermission(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 项名称 |
| 返回值 |  |
| 字段 |  |