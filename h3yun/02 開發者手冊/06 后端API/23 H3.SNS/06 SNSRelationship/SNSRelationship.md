---
title: "SNSRelationship"
source: "https://help.h3yun.com/contents/677/781.html"
category: "開發者手冊 / 后端API / H3.SNS / SNSRelationship"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : SNSRelationship
说明 : 用于记录用户的评论 属性 : 

| 名称 | 说明 |
| --- | --- |
| SchemaCode | 业务对象模式编码 |
| UserId | 用户ID |
| Follow | 关系的类型，默认是关注所有有权限的对象 |
| Notify | 是否自动通知 |
| IsDefault | 如果是默认的配置，则返回true，默认的配置是指Follow==true。默认模式的配置，不会在数据库中存储 |