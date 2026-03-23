---
title: "Urgency"
source: "https://help.h3yun.com/contents/658/426.html"
category: "開發者手冊 / 后端API / H3.Workflow.WorkItem / Urgency"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : Urgency
说明 : 催办信息，催办是指，当用户A发现某个未完成流程实例处于延期或者其他状况的时候，用户A可以对这个流程实例进行催办，这个催办会发给这个流程实例的所有的未完成工作项 属性 : 

| 名称 | 说明 |
| --- | --- |
| UrgencyId | ID |
| Urger | 催办人 |
| WorkItemId | 催办的工作项ID |
| InstanceId | 催办的流程ID |
| Content | 催办的内容 |
| UrgeTime | 催办的时间 |
| BatchId | 批次 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_Urger | 属性名称 |
| PropertyName\_WorkItemId | 属性名称 |
| PropertyName\_InstanceId | 属性名称 |
| PropertyName\_Content | 属性名称 |
| PropertyName\_UrgeTime | 属性名称 |
| PropertyName\_BatchId | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "urger" | 催办人 |
| "instanceId" | 流程实例ID |
| "batchId" | 批次ID，对于同一次的催办，批次ID是相同的。当用户A发现某个未完成流程实例处于延期或者其他状况的时候，用户A可以对这个流程实例进行催办，这个催办会发给这个流程实例的所有的未完成工作项，那么所有这些工作项的催办的批次都是相同的 |
| "workItemId" | 该催办记录对应的工作项的ID |
| "content" | 催办的内容 |
| 返回值 |  |
| |
 |