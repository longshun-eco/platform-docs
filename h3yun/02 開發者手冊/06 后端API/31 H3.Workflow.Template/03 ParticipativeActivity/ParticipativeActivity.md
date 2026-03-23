---
title: "ParticipativeActivity"
source: "https://help.h3yun.com/contents/707/462.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / ParticipativeActivity"
updated: 2025-12-14
tags:
  - h3yun
  - 開發者手冊
---
类名 : ParticipativeActivity
说明 : 用户参与的活动 属性 : 

| 名称 | 说明 |
| --- | --- |
| FinishExit | 完成出口条件，必须为整数或者某一个数据项的名称，请注意不是{InstanceData\["..."\].Value}的形式 |
| PermittedActions | 允许进行的操作 |
| ParticipateMethod | 活动多用户参与模式，并行/串行 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : IsExitAcceptable(System.String)

| 参数 | 说明 |
| --- | --- |
| "Exit" | 出口条件的设置 |
| 返回值 |  |
| 返回出口条件是否可以被解析 |  |


方法名称 : IsExitInt(System.String,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "Exit" | 出口条件的设置 |
| "Value" | 如果出口条件是整数，那么在这里返回出口条件的值 |
| 返回值 |  |
| 如果出口条件是整数，则返回true，否则返回false |  |


方法名称 : IsExitPercent(System.String,System.Double@)

| 参数 | 说明 |
| --- | --- |
| "Exit" | 出口条件的设置 |
| "Rate" | 如果出口条件是一个比率，那么在这里返回出口条件的值 |
| 返回值 |  |
| 如果出口条件是一个比率，则返回true，否则返回false |  |


方法名称 : ParseExit(H3.Workflow.Instance.InstanceData,System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "InstanceData" | 流程实例数据对象，通过该对象可以访问流程数据项的值，引用的业务对象的值等信息 |
| "Exit" | 出口条件的设置 |
| "Total" | 总参与者数量 |
| 返回值 |  |
| 出口条件的值，如果出口条件设置的是一个固定的值，则返回该值；如果是一个比率，则用该比率\*Total |  |


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
| "XmlDocument" | |
| "XmlElement" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "XmlElement" | |
| 返回值 |  |
| |
 |