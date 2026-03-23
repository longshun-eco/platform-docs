---
title: "BizObjectSeqNo"
source: "https://help.h3yun.com/contents/358/373.html"
category: "開發者手冊 / 后端API / H3.DataModel / BizObjectSeqNo"
updated: 2025-12-19
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizObjectSeqNo
说明 : 数据模式的流水号 属性 : 

| 名称 | 说明 |
| --- | --- |
| SchemaCode | 模式编码 |
| ModifiedTime | 最后一次修改时间 |
| NextSeqId | 流水号，从1开始计数，每新增一个对象就加1 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_SchemaCode | 属性名称 |
| PropertyName\_ModifiedTime | 属性名称 |
| PropertyName\_NextSeqId | 属性名称 |
| UnspecifiedSequenceId | 未指定的流水号 |
| InitialSequenceId | 初始流水号 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 模式编码 |
| 返回值 |  |
| |  |


方法名称 : CreateSeqNo(System.String,System.Int32,H3.DataModel.BizObjectSeqNoDateFormat,System.DateTime,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "seqNoPrefix" | 流水号的前置字符串 |
| "seqNoLength" | 流水号的长度 |
| "dateFormat" | 流水号的日期格式 |
| "now" | 当前时间 |
| "seqId" | 流水号的顺序号 |
| 返回值 |  |
| 新建的流水号 |  |


方法名称 : GetKeyNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 返回索引名称 |  |


方法名称 : GetKeyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "KeyName" | 属性值 |
| 返回值 |  |
| 返回索引值 |  |