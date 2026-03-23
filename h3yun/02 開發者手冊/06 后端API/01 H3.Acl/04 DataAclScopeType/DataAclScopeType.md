---
title: "DataAclScopeType"
source: "https://help.h3yun.com/contents/301/297.html"
category: "開發者手冊 / 后端API / H3.Acl / DataAclScopeType"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : DataAclScopeType
说明 : 组织结构范围类型 
成员 : 

| 名称 | 说明 |
| --- | --- |
| None | 不具备权限，不能配置一个Schema的数据权限是None，如果是None，则应该删掉这条数据权限记录。None主要是用于查询和计算。 |
| Own | 自身权限，用户能访问自己是Owner的对象 |
| OwnDept | 某个特定的组织，用户能访问Owner隶属于自己角色管理的部门 |
| All | 所有对象 |