---
title: "BizObjectPropertyTrack"
source: "https://help.h3yun.com/contents/379/412.html"
category: "開發者手冊 / 后端API / H3.DataModel / BizObjectPropertyTrack"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizObjectPropertyTrack
说明 : 数据项的痕迹记录 属性 : 

| 名称 | 说明 |
| --- | --- |
| BizObjectId | 流程ID |
| PropertyName | 数据项名称 |
| ModifiedBy | 修改人 |
| ModifiedValue | 修改后的值 |
| ModifiedTime | 修改时间 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_BizObjectId | 流程ID列名 |
| PropertyName\_PropertyName | 数据项名称列名 |
| PropertyName\_ModifiedBy | 属性名称 |
| PropertyName\_ModifiedValue | 存储修改后的值的列的列名 |
| PropertyName\_ModifiedTime | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.String,System.Object)

| 参数 | 说明 |
| --- | --- |
| "bizObjectId" | 流程实例的ID |
| "propertyName" | 项名称 |
| "modifiedBy" | 修改数据的人 |
| "modifiedValue" | 修改后的值 |
| 返回值 |  |