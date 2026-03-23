---
title: "ExceptionLog"
source: "https://help.h3yun.com/contents/333/337.html"
category: "開發者手冊 / 后端API / H3.Clusterware.Log / ExceptionLog"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : ExceptionLog
说明 : 集群中每个服务器的设置，包括服务器地址、负载等 属性 : 

| 名称 | 说明 |
| --- | --- |
| EngineCode | 引擎的编码 |
| ExceptionType | 异常的类型 |
| Milliseconds | 如果是超时异常，那么在这里记录时长，毫秒数 |
| UserCode | 用户的编码 |
| AppCode | 应用的编码 |
| ModuleName | 应用的模块 |
| ActionName | 应用的模块 |
| Message | 异常的整个的ToString的内容 |
| Message1 | 异常的整个的ToString的内容 |
| Message2 | 异常的整个的ToString的内容 |
| Parameters | 调用该方法的参数 |
| CreatedTime | 超过一定时间则会自动失效 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_EngineCode | 属性名称 |
| PropertyName\_ExceptionType | 属性名称 |
| PropertyName\_Milliseconds | 属性名称 |
| PropertyName\_UserCode | 属性名称 |
| PropertyName\_AppCode | 属性名称 |
| PropertyName\_ModuleName | 属性名称 |
| PropertyName\_ActionName | 属性名称 |
| PropertyName\_Message1 | 属性名称 |
| PropertyName\_Message2 | 属性名称 |
| PropertyName\_Parameters | 属性名称 |
| PropertyName\_CreatedTime | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |