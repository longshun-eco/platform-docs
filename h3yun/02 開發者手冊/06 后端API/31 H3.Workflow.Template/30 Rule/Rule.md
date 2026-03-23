---
title: "Rule"
source: "https://help.h3yun.com/contents/734/560.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / Rule"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : Rule
说明 : 流程模板中的连接线，也就是路由规则 属性 : 

| 名称 | 说明 |
| --- | --- |
| DisplayName | 显示名称 |
| IsActivity | 是否活动 |
| IsRule | 是否路由 |
| PreActivityCode | 前驱活动的编码 |
| PostActivityCode | 后继活动的编码 |
| Exclusive | 是否排他的，如果是排他的，当其他路由都不满足条件的时候，走该路由，一个分支中允许有多个路由规则使用Exclusive机制 |
| FixedPoint | 是否固定点,如果固定,每次调整线条时,最小化调整,否则自动重新计算 |
| TextX | 获取或设置路由文字的位移:X |
| TextY | 获取或设置路由文字的位移:Y |
| Points | 获取或设置线条的点 |
| FormulaText | 规则文本 |
| Formula | 是否使用Else，如果使用Else表示，当其他路由都不满足条件的时候，走该路由，一个分支中允许有多个路由规则使用Else机制 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| \_TextX | 文字位移:X |
| \_TextY | 文字位移:Y |


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
| |
 |
| 返回值 |  |
| |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlDocument" | |
| "xmlElement" | |
| 返回值 |  |
| |
 |