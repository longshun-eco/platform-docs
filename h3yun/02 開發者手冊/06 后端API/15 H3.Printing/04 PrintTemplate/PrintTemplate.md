---
title: "PrintTemplate"
source: "https://help.h3yun.com/contents/515/404.html"
category: "開發者手冊 / 后端API / H3.Printing / PrintTemplate"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : PrintTemplate
说明 : 打印模板 属性 : 

| 名称 | 说明 |
| --- | --- |
| SchemaCode | 唯一编码 |
| PageSetting | 页面设置 |
| MaxPageIndex | 最大页数 |
| Properties | 打印显示字段及对应属性 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName\_PrintTime | 属性节点 |
| DefaultDisplayName\_PrintTime | 属性节点 |
| PropertyName\_Printer | 属性节点 |
| DefaultDisplayName\_Printer | 属性节点 |
| PropertyName\_Originator | 属性节点 |
| DefaultDisplayName\_Originator | 属性节点 |
| PropertyName\_QRCode | 属性节点 |
| DefaultDisplayName\_QRCode | 属性节点 |
| PropertyName\_BarCode | 属性节点 |
| DefaultDisplayName\_BarCode | 属性节点 |
| PropertyName\_WorkFlowLog | 属性节点 |
| DefaultDisplayName\_WorkFlowLog | 属性节点 |
| PropertyName\_WorkFlowStamp | 属性节点 |
| DefaultDisplayName\_WorkFlowStamp | 属性节点 |
| XmlNodeName | 打印模板XML的根节点名称 |
| Property\_PageSetting | 页面设置 |
| Property\_Properties | 属性节点 |
| Property\_Suffix | 属性节点后缀 |
| Property\_Background | 背景图存储字段属性 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String)

| 参数 | 说明 |
| --- | --- |
| "xmlContent" | |
| 返回值 |  |
| |  |


方法名称 : \_printDocument(System.String)

| 参数 | 说明 |
| --- | --- |
| "xmlContent" | 流程模板的Xml |
| 返回值 |  |
| |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlDocument" | |
| "xmlElement" | |
| 返回值 |  |
| |  |


方法名称 : GetXmlContent

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |