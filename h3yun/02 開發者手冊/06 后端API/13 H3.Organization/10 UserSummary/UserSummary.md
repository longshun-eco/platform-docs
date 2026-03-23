---
title: "UserSummary"
source: "https://help.h3yun.com/contents/481/591.html"
category: "開發者手冊 / 后端API / H3.Organization / UserSummary"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : UserSummary
说明 : 用户信息 属性 : 

| 名称 | 说明 |
| --- | --- |
| ObjectId | ObjectId |
| Name | 名称 |
| Mobile | 手机号 |
| State | 状态 |
| ParentId | 父Id |
| IsManager | 是否是经理 |
| ParentName | 所在部门名称 |
| ServiceUnitNames | 服务部门名称 |
| Email | 邮箱 |
| ProfilePhotoUrl | 头像 |



构造方法名称 : #ctor(System.String,System.String,System.String,H3.Organization.State,System.String,System.Boolean,System.String)

| 参数 | 说明 |
| --- | --- |
| "objectId" | ObjectId |
| "name" | 名称 |
| "mobile" | 手机号 |
| "state" | 状态 |
| "parentId" | 所在部门Id |
| "isManager" | 是否是经理 |
| "parentName" | 父节点名称 |
| 返回值 |  |