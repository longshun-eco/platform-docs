---
title: "InvokeResultBase"
source: "https://help.h3yun.com/contents/629/713.html"
category: "開發者手冊 / 后端API / H3.BizBus / InvokeResultBase"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : InvokeResultBase
说明 : 调用接口的时候返回值的基类 属性 : 

| 名称 | 说明 |
| --- | --- |
| Code | 获取或设置执行的结果的代码，0：成功；1：未命名的失败；其他：其他命名的错误代码。如果是外部系统调用H3的接口，那么这里返回的值跟H3.ErrorCode对应 |
| Message | 错误信息 |
| Schema | 数据模型 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |