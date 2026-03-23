---
title: "ClientActivity"
source: "https://help.h3yun.com/contents/708/466.html"
category: "開發者手冊 / 后端API / H3.Workflow.Template / ClientActivity"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : ClientActivity
说明 : 与相关的活动，该类继承自Activity，只是多了Participants属性 属性 : 

| 名称 | 说明 |
| --- | --- |
| WorkItemDisplayName | 获取或设置任务显示名称 |
| PropertyPermissions | 数据权限 |
| DuplicatedParticipantPolicy | 如果活动参与者与上一个参与者相同，采取策略 |
| NoParticipantPolicy | 如果没有参与者，采取策略 |
| AllowedTime | 许可的时间。可以是时间段类型的值/数据项(取消) 浮点型值 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName\_AllowedTime | 许可的时间 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetPropertyVisible(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 数据项名称 |
| 返回值 |  |
| 数据项是否可见 |  |


方法名称 : GetPropertyEditable(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 数据项名称 |
| "startActivityCode" | 启动活动节点 |
| 返回值 |  |
| 数据项是否可以编辑 |  |


方法名称 : GetPropertyTrackVisible(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 数据项名称 |
| 返回值 |  |
| 数据项的变更日志是否可见 |  |


方法名称 : GetPropertyRequired(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 数据项名称 |
| 返回值 |  |
| 数据项是否必填 |  |


方法名称 : GetPropertyPrintable(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 数据项名称 |
| 返回值 |  |
| 数据项是否可打印 |  |


方法名称 : GetChildPropertyVisible(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 主表字段的名称 |
| "childPropertyName" | 子表字段的名称 |
| 返回值 |  |
| 是否可见 |  |


方法名称 : GetChildPropertyEditable(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 主表字段的名称 |
| "childPropertyName" | 子表字段的名称 |
| "startActivityCode" | 启动活动节点 |
| 返回值 |  |
| 是否可以编辑 |  |


方法名称 : GetChildPropertyTrackVisible(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 主表字段的名称 |
| "childPropertyName" | 子表字段的名称 |
| 返回值 |  |
| 变更日志是否可见 |  |


方法名称 : GetChildPropertyRequired(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 主表字段的名称 |
| "childPropertyName" | 子表字段的名称 |
| 返回值 |  |
| |  |


方法名称 : GetChildPropertyPrintable(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 主表字段的名称 |
| "childPropertyName" | 子表字段的名称 |
| 返回值 |  |
| 是否可以打印 |  |


方法名称 : Validate(H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "Schema" | |
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