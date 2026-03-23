---
title: "PrintProperty"
source: "https://help.h3yun.com/contents/525/427.html"
category: "開發者手冊 / 后端API / H3.Printing.Property / PrintProperty"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : PrintProperty
说明 : 打印属性基类 属性 : 

| 名称 | 说明 |
| --- | --- |
| Text | 文本值 |
| PropertyType | 属性类型 |
| Code | 属性编码(唯一标识) |
| DataField | 字段编码（取数据） |
| IsInSubTable | 是否在子表中 |
| DisplayName | 显示名称 |
| PointX | X轴坐标 |
| PointY | Y轴坐标 |
| Width | 宽度 |
| Height | 高度 |
| PrintAtFirst | 在第一页打印 |
| PrintAtMiddle | 在中间页打印 |
| PrintAtLast | 在最后一页打印 |
| DefaultValue | 默认属性值 |
| Value | 属性值 |
| PageIndex | 第几页 |
| TextSource | 文本来源(固定文本或表单字段) |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Printing.Enum.PrintPropertyType)

| 参数 | 说明 |
| --- | --- |
| "propertyType" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlElement" | |
| 返回值 |  |
| |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlDocument" | |
| "xmlElement" | |
| 返回值 |  |