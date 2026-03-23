---
title: "ClientActivityBase"
source: "https://help.h3yun.com/contents/715/488.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / ClientActivityBase"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : ClientActivityBase
说明 : 用户参与的活动 属性 : 

| 名称 | 说明 |
| --- | --- |
| Participants | 当前活动的默认参与者。这个属性中的参与者并不直接对应到具体的人 |
| ParticipateType | 获取或设置参与者方式，单人/多人/全部参与 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : ParseParticipants(H3.Workflow.Instance.InstanceData,H3.Organization.IOrganization)

| 参数 | 说明 |
| --- | --- |
| "InstanceData" | 流程实例数据对象，通过该对象可以访问流程数据项的值，引用的业务对象的值等信息 |
| "Organization" | 组织对象管理器 |
| 返回值 |  |
| 指向具体人员的参与者 |  |


方法名称 : ParseParticipants(System.String,H3.Workflow.Instance.InstanceData,H3.Organization.IOrganization)

| 参数 | 说明 |
| --- | --- |
| "RawParticipants" | 定义的参与者，这些参与者并不会直接指向某个具体的用户，而是类似于Originator.ManagerID之类的 |
| "InstanceData" | 流程实例数据对象，通过该对象可以访问流程数据项的值，引用的业务对象的值等信息 |
| "Organization" | 组织对象管理器 |
| 返回值 |  |
| 指向具体人员的参与者 |  |


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


方法名称 : Validate(H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "Schema" | |
| 返回值 |  |
| |
 |