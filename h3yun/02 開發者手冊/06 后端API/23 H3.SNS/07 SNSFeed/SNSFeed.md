---
title: "SNSFeed"
source: "https://help.h3yun.com/contents/678/783.html"
category: "開發者手冊 / 后端API / H3.SNS / SNSFeed"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : SNSFeed
说明 : 用于记录用户的动态 属性 : 

| 名称 | 说明 |
| --- | --- |
| UserId | 用户ID |
| AppCode | 应用的ID |
| CreatedTime | 用户ID |
| FeedType | 新闻的类型 |
| Sender | 触发者，如果是创建了一个BO，那么这里记录创建BO的人；如果是添加了一条评论，则记录评论人 |
| SchemaCode | 业务对象模式编码 |
| BizObjectId | 业务对象ID |
| TargetId | 通知的对象的ID，工作项或者流程实例的ID |
| TargetName | 通知的对象的名称 |
| TargetId2 | 通知的对象的ID2，比如：流程实例的ID |
| TargetName2 | 通知的对象的名称2 |
| Text | 添加的评论的内容 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_UserId | 属性名称 |
| PropertyName\_AppCode | 属性名称 |
| PropertyName\_CreatedTime | 属性名称 |
| PropertyName\_FeedType | 属性名称 |
| PropertyName\_Sender | 属性名称 |
| PropertyName\_SchemaCode | 属性名称 |
| PropertyName\_BizObjectId | 属性名称 |
| PropertyName\_TargetId | 属性名称 |
| PropertyName\_TargetName | 属性名称 |
| PropertyName\_TargetId2 | 属性名称 |
| PropertyName\_TargetName2 | 属性名称 |
| PropertyName\_Text | 属性名称 |


方法名称 : GetTableName(System.Char)

| 参数 | 说明 |
| --- | --- |
| "userIdPrefix" | 用户的Id的首字符 |
| 返回值 |  |
| 用户的动态表名称 |  |


方法名称 : GetTableNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 系统中所有的动态表 |  |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |