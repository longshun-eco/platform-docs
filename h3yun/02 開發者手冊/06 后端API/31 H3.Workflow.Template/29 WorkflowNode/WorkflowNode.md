---
title: "WorkflowNode"
source: "https://help.h3yun.com/contents/733/557.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / WorkflowNode"
updated: 2025-12-19
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkflowNode
说明 : 流程模板结点基类 属性 : 

| 名称 | 说明 |
| --- | --- |
| IsActivity | 是否活动 |
| IsRule | 是否路由 |
| FontSize | 字体大小 |
| FontColor | 字体颜色 |
| Id | ID |



成员 : 

| 名称 | 说明 |
| --- | --- |
| NullWorkflowNodeID | 空的节点ID |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlElement" | |
| 返回值 |  |
| |  |


方法名称 : Validate(H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "schema" | 流程模板对应的业务对象模式 |
| 返回值 |  |
| 如果没有错误，则返回true，否则返回false |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlDocument" | Xml文档 |
| "xmlElement" | Xml元素 |
| 返回值 |  |
| |
 |