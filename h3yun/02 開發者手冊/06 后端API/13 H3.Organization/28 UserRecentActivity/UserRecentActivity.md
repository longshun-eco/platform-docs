---
title: "UserRecentActivity"
source: "https://help.h3yun.com/contents/499/646.html"
category: "開發者手冊 / 后端API / H3.Organization / UserRecentActivity"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : UserRecentActivity
说明 : 用户的最近访问记录 属性 : 

| 名称 | 说明 |
| --- | --- |
| UserId | 用户Id |
| Templates | 设置类型 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_UserId | 属性名称 |
| MaxTemplateCount | 最近访问的模板的数量 |
| PropertyName\_Templates | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetKeyNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetKeyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "KeyName" | |
| 返回值 |  |
| |  |


方法名称 : AddTemplate(H3.Organization.RecentTemplateType,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "type" | |
| "code" | |
| "name" | |
| 返回值 |  |