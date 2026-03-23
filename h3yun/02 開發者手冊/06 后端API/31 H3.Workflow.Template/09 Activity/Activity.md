---
title: "Activity"
source: "https://help.h3yun.com/contents/713/483.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / Activity"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : Activity
说明 : 活动模板 属性 : 

| 名称 | 说明 |
| --- | --- |
| ActivityType | 获取或设置活动类型 |
| DisplayName | 显示名称 |
| ToolTipText | 提示文字 |
| ActivityCode | 活动编码，这个主要是为了跟流程体系管理的活动编号对应 |
| SortKey | 排序键 |
| Height | 获取或设置节点显示宽度 |
| Width | 获取或设置节点显示宽度 |
| X | 获取或设置活动中心点的位移X |
| Y | 获取或设置活动中心点的位移Y |
| IsActivity | 是否活动 |
| IsRule | 是否路由 |
| IsEnd | 是否是结束结点，如果是则当执行完动作序列后结束整个实例 |
| IsApproveActivity | 是否是审批类型的活动，在旧版本中是没有该属性的，所以不能通过该属性来判断当前活动是否一定是审批活动。 |
| IsClient | 是否是人工参与类型的活动 |
| EntryCondition | 获取或设置活动的前置条件，当为All时，则具有聚合作用 |
| FullName | 全名称 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName\_Height | 节点显示高度 |
| PropertyName\_Width | 节点显示宽度 |
| PropertyName\_X | 活动中心点的位移X |
| PropertyName\_Y | 活动中心点的位移Y |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlDocument" | |
| "xmlElement" | |
| 返回值 |  |
| |  |


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
| "Schema" | |
| 返回值 |  |
| |  |


方法名称 : GetFullName(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "ActivityCode" | |
| "DisplayName" | |
| 返回值 |  |
| |  |


方法名称 : GetDefaultActivityTemplates

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |