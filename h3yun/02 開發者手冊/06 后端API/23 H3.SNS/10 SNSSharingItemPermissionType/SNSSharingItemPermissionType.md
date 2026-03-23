---
title: "SNSSharingItemPermissionType"
source: "https://help.h3yun.com/contents/681/788.html"
category: "開發者手冊 / 后端API / H3.SNS / SNSSharingItemPermissionType"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : SNSSharingItemPermissionType
说明 : 分享项目的权限类型 
成员 : 

| 名称 | 说明 |
| --- | --- |
| NoAccess | 禁止访问，这个类型并不存储起来，在SharingItem表中，如果权限类型为该类型，则从这个表中删除这条记录 |
| ReadOnly | 只读 |
| Writable | 可写 |