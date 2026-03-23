---
title: "InvokeResult"
source: "https://help.h3yun.com/contents/633/722.html"
category: "開發者手冊 / 后端API / H3.BizBus / InvokeResult"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : InvokeResult
说明 : 调用返回结果 属性 : 

| 名称 | 说明 |
| --- | --- |
| Data | 调用接口后，返回的数据 |
| Schema | 数据模型 |



构造方法名称 : #ctor(System.Int32,System.String,H3.BizBus.BizStructure)

| 参数 | 说明 |
| --- | --- |
| "resultCode" | 获取或设置执行的结果的代码，0：成功；1：未命名的失败；其他：其他命名的错误代码。如果是外部系统调用H3的接口，那么这里返回的值跟H3.ErrorCode对应 |
| "message" | 错误消息 |
| "data" | 返回数据 |
| 返回值 |  |
| |  |