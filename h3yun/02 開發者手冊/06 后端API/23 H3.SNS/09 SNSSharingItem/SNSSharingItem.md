---
title: "SNSSharingItem"
source: "https://help.h3yun.com/contents/680/787.html"
category: "開發者手冊 / 后端API / H3.SNS / SNSSharingItem"
updated: 2025-12-14
tags:
  - h3yun
  - 開發者手冊
---
类名 : SNSSharingItem
说明 : 用于统一记录用户的全部任务 属性 : 

| 名称 | 说明 |
| --- | --- |
| Sender | 发送分享的人 |
| TargetType | 分享的对象的类型 |
| SchemaCode | 业务对象模式编码，如果当前项目是业务对象，那么这里记录的是业务对象模式编码，否则为空 |
| BizObjectId | 业务对象ID |
| TargetId | 对象的ID，如果当前项目是WorkItem，那么这里记录的是WorkItemId；如果是BizObject，那么这里记录的是BizObjectId |
| Permission | 权限类型，比如是否可写 |
| IsPublic | 是否是公开的 |
| InternalReceivers | 要分享给的内部用户集合 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_Sender | 属性名称 |
| PropertyName\_TargetType | 属性名称 |
| PropertyName\_SchemaCode | 属性名称 |
| PropertyName\_BizObjectId | 属性名称 |
| PropertyName\_TargetId | 属性名称 |
| PropertyName\_Permission | 属性名称 |
| PropertyName\_IsPublic | 属性名称 |
| PropertyName\_InternalReceivers | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : CheckInternalReceivers(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "memberOfs" | 组织机构Id |
| 返回值 |  |
| 如果分享的内容用户包含任一memberOfs对象，则返回true，否则返回false |  |