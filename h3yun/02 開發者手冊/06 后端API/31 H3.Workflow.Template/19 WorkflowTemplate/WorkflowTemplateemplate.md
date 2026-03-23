---
title: "WorkflowTemplateemplate"
source: "https://help.h3yun.com/contents/723/518.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / WorkflowTemplate"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : WorkflowTemplate
说明 : 流程模板，所有流程的运行都基于流程模板 属性 : 

| 名称 | 说明 |
| --- | --- |
| StartWithForm | 开始环节需要填写表单 |
| StartActivityCode | 开始活动编码,即"开始"后的第一个活动编码 |
| EndActivityCode | 结束活动编码 |
| StartActivity | 开始活动，流程实例将从这个活动开始执行:活动类型为FillSheet |
| EndActivity | 结束活动:活动类型为结束 |
| WorkflowVersion | 流程模板版本号 |
| WorkflowFullName | 获取全名称 |
| Description | 描述 |
| PlanUsedTime | 计划使用时间，这个字段可以是一个数据项也可以是一个具体的时间段 |
| Height | 获取或设置高度 |
| Width | 获取或设置宽度 |
| SchemaCode | 业务对象模式编码 |
| Activities | 所有活动 |
| Rules | 路由 |
| InstanceName | 流程名称来源 |
| WorkflowName | 流程模板名称 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| NullWorkflowVersion | 空的流程版本号 |
| MaxFullNameLen | 名称最大长度，表名为I\_WorkflowPackageName\_WorkflowName，表名最大长度为30，所以总共的最大长度是(30 - 3) / 2 |
| XmlNodeName | 流程模板XML的根节点名称 |
| ActivityCodeTable | (ActivityCode, Activity)表，但是Code为空的活动不在这个表内 |
| RuleTable | 路由表: (PartID,Rule) |
| \_PreActivityRulesTable | 以活动为开始的规则集合，(活动Code，活动后续的规则ID数组) |
| \_PostActivityRulesTable | 以活动为结束的规则集合，(活动ID，活动前置的规则ID数组) |
| \_WorkflowVersion | 版本号 |
| \_Height | 高度 |
| \_SchemaCode | 业务对象模式编码 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "xmlContent" | Xml的内容 |
| "workflowVersion" | 流程模板的版本号 |
| 返回值 |  |
| |  |


方法名称 : \_WorkflowDocument(System.String)

| 参数 | 说明 |
| --- | --- |
| "xmlContent" | 流程模板的Xml |
| 返回值 |  |
| |  |


方法名称 : Validate(H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "schema" | 流程关联的业务对象模式 |
| 返回值 |  |
| 如果验证成功则返回Valid为true的验证结果，否则返回错误信息 |  |


方法名称 : GetStartActivities

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetEndActivities

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetActivityByCode(System.String)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 活动编码 |
| 返回值 |  |
| 活动模板信息 |  |


方法名称 : SortActivities(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "activityCodes" | 活动的编码 |
| 返回值 |  |
| 排序后的活动的名称 |  |


方法名称 : GetRule(System.Int32)

| 参数 | 说明 |
| --- | --- |
| "partId" | 规则ID |
| 返回值 |  |
| 规则模板 |  |


方法名称 : BuildConnections

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetActivityPostRules(System.String)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 节点编码 |
| 返回值 |  |
| 后续的连接线 |  |


方法名称 : GetActivityPostActivities(System.String)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 活动名称 |
| 返回值 |  |
| 后续活动 |  |


方法名称 : GetActivityPreActivities(System.String)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 流程活动的名称，该活动名称在流程设计器中定义 |
| 返回值 |  |
| 活动的前驱活动 |  |


方法名称 : GetActivityPreActivityCodes(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 活动编码 |
| "recursive" | 是否递归获得前驱 |
| 返回值 |  |
| 前驱的活动的名称 |  |


方法名称 : GetActivityPreActivityCodes(System.String)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 活动的编码 |
| 返回值 |  |
| 活动的前驱活动的编码 |  |


方法名称 : GetActivityPreRules(System.String)

| 参数 | 说明 |
| --- | --- |
| "activityCode" | 流程活动的编码，该活动编码在流程设计器中定义 |
| 返回值 |  |
| 活动后续的连接线 |  |


方法名称 : GetSplitter(System.String\[\],System.Collections.Generic.List{System.String})

| 参数 | 说明 |
| --- | --- |
| "activities" | 要获得共同的分支的活动的名称 |
| "preActivies" | 获取的前驱路由集合 |
| 返回值 |  |
| 如果存在共同的分支，则返回共同的分支的编码，否则返回null |  |


方法名称 : Dist(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "fromActivity" | 起始活动 |
| "endActivity" | 目的活动 |
| 返回值 |  |
| 两个活动之间间隔的活动的数量 |  |


方法名称 : GetWorkflowFullName(System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程模板版本号 |
| 返回值 |  |
| 流程模板全名 |  |


方法名称 : ParseWorkflowFullName(System.String,System.String@,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "fullName" | 流程模板全名称 |
| "schemaCode" | 流程模板编码 |
| "workflowVersion" | 流程模板版本号 |
| 返回值 |  |
| |  |


方法名称 : ParseUsedTime(H3.Workflow.Instance.InstanceData,System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceData" | 流程数据 |
| "planUserTimeText" | 计划时间的文本 |
| 返回值 |  |
| 具体的计划时长 |  |


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
| |
 |