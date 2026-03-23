---
title: "EngineUsage"
source: "https://help.h3yun.com/contents/337/341.html"
category: "開發者手冊 / 后端API / H3.Clusterware.Operation / EngineUsage"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : EngineUsage
说明 : 一个引擎的使用情况 属性 : 

| 名称 | 说明 |
| --- | --- |
| Code | 引擎的编码 |
| Name | 引擎的名称 |
| DailyActiveUserCount | 日活 |
| WeeklyActiveUserCount | 周活 |
| MonthlyActiveUserCount | 月活 |
| FileSize | 文件的总大小 |
| DbSize | 数据库的总大小 |
| ActiveUserCount | 生效的用户数 |
| TotalBizObjectCount | 系统中所有的业务对象的数量 |
| SolutionCount | /解决方案数量 |
| AppCount | 应用数量 |
| SchemaCount | 数据模型数据数 |
| MonthlyBizObjectCount | 本月新建的业务对象的数量 |
| Solutions | 解决方案的使用情况 |
| AppNames | 应用名称 |
| Admins | 管理员信息 |
| LastLoginTime | 最后一次登录时间 |



构造方法名称 : #ctor(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | |
| 返回值 |  |
| |  |


方法名称 : GetSolution(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | 解决方案编码 |
| 返回值 |  |
| 使用情况 |  |