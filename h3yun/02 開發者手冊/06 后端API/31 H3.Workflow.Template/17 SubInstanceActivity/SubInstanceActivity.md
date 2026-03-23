---
title: "SubInstanceActivity"
source: "https://help.h3yun.com/contents/721/511.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / SubInstanceActivity"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : SubInstanceActivity
说明 : 子流程活动 属性 : 

| 名称 | 说明 |
| --- | --- |
| ActivityType | 获取当前活动节点类型 |
| SchemaCode | 获取或设置子流程的模板编码 |
| WorkflowVersion | 获取或设置子流程的流程模型版本号 |
| Sync | 获取或设置是否同步子流程 |
| FinishStartActivity | 获取或设置是否自动结束子流程的第一个活动 |
| ParticipateMethod | 活动多用户参与模式，并行/串行 |
| DataMaps | 获取或设置父子流程数据项映射 |
| ApproveExit | 同意出口条件，必须为整数或者某一个数据项的名称，请注意不是{InstanceData\["..."\].Value}的形式 |
| DisapproveExit | 拒绝出口条件，必须为整数或者某一个数据项的名称，请注意不是{InstanceData\["..."\].Value}的形式 |
| FinishExit | 完成出口条件，必须为整数或者某一个数据项的名称，请注意不是{InstanceData\["..."\].Value}的形式 |



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
| "schema" | |
| 返回值 |  |
| |  |


方法名称 : SaveAsXml(System.Xml.XmlDocument,System.Xml.XmlElement)

| 参数 | 说明 |
| --- | --- |
| "xmlDocument" | |
| "xmlElement" | |
| 返回值 |  |
| |  |