---
title: "ParentInstanceInfo"
source: "https://help.h3yun.com/contents/689/755.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance / ParentInstanceInfo"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : ParentInstanceInfo
说明 : 父流程模板的基本信息 属性 : 

| 名称 | 说明 |
| --- | --- |
| ParentInstanceId | 父流程ID |
| ParentTokenId | 父流程的流程模板的活动的令牌ID |
| ParentSchemaCode | 父流程流程模板类型 |
| ParentWorkflowVersion | 父流程流程模板版本号 |
| ParentActivityName | 父流程的流程模板的活动 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.Int32,System.String,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "parentInstanceId" | 父流程ID |
| "parentSchemaCode" | 父流程流程模板编码 |
| "parentWorkflowVersion" | 父流程流程模板版本号 |
| "parentActivityName" | 父流程的流程模板的活动 |
| "parentActivityTokenId" | 父流程的流程模板的活动的令牌ID |
| 返回值 |  |
| |
 |