---
title: "BizObjectFolderAcl"
source: "https://help.h3yun.com/contents/304/302.html"
category: "開發者手冊 / 后端API / H3.Acl / BizObjectFolderAcl"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizObjectFolderAcl
说明 : 文档库目录的权限，指定某个组织对于该目录的访问权限 属性 : 

| 名称 | 说明 |
| --- | --- |
| OrgId | 组织Id，可以是UnitId或者OrgId |
| SchemaCode | 业务对象模式编码 |
| FolderId | 要设置的目录权限的目录的Id，如果为空，则表示是根目录 |
| Write | 是否具有写权限 |
| Read | 是否具有查看权限 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_OrgId | 属性名称 |
| PropertyName\_SchemaCode | 属性名称 |
| PropertyName\_FolderId | 属性名称 |
| PropertyName\_Write | 新增权限 属性名称 |
| \_Write | 新增权限 |
| PropertyName\_Read | 查看权限属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Check(H3.Acl.AclType)

| 参数 | 说明 |
| --- | --- |
| "aclType" | 要检查的权限类型 |
| 返回值 |  |
| 如果具有该权限，则返回true，否则返回false。其中，如果用户拥有管理权限，在这里检查是否具有读权限，那么也会返回true |  |