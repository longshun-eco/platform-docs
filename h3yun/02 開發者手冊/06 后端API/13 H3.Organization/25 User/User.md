---
title: "User"
source: "https://help.h3yun.com/contents/496/638.html"
category: "開發者手冊 / 后端API / H3.Organization / User"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : User
说明 : 用户，这是组织结构树中的叶子节点，如果与活动目录同步的话，用户的属性会自动与活动目录中的用户属性保持同步 属性 : 

| 名称 | 说明 |
| --- | --- |
| UnitType | 类型 |
| FullName | 全名 |
| Birthday | 生日 |
| Gender | 性别 |
| EntryDate | 入职日期 |
| DepartureDate | 离职日期 |
| EmployeeNumber | 员工编号，流程系统本身只是引用该字段。该字段不是必填字段，但是，一旦填写，必须唯一 |
| Title | 用户的职务 |
| HomePhone | 家庭电话号码 |
| OfficePhone | 办公室电话 |
| QQ | QQ |
| IdNumber | 身份证号码 |
| EmployeeRank | 获取或设置员工职级 |
| ProfilePhotoUrl | 头像的链接地址 |
| DepartmentName | 部门名称，对于内部用户，这个字段并不存储在数据库中；对于外部用户，这个字段存储在数据库中 |
| Password | 密码 |
| Mobile | 手机 |
| Email | 邮件 |
| DingTalkAccount | 获取或设置用户的DingTalkId |
| DingId | 获取或设置用户的DingId |
| WeChatUserId | 获取或设置用户的微信id |
| Position | 获取或设置用户的职位 |
| ExtAttr | 额外属性 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 对应的表名称 |
| ExternalTableName | 对应的表名称 |
| ExternalObjectIdPrefix | 外部前缀 |
| CodeMaxLen | Alias的最大名称 |
| SystemUserId | 系统账号Id |
| SystemUserLoginName | 系统账号登录名。系统账户只能在后台进行操作，不允许在前台做操作，不接收任何消息，在组织结构中也不可见 |
| AnonymousUserId | 匿名用户的Id |
| AnonymousUserLoginName | 匿名用户的名称 |
| PropertyName\_Birthday | 属性名称 |
| PropertyName\_Gender | 性别属性名称 |
| PropertyName\_EntryDate | 属性名称 |
| PropertyName\_DepartureDate | 属性名称 |
| PropertyName\_EmployeeNumber | 属性名称 |
| PropertyName\_Title | 属性名称 |
| PropertyName\_HomePhone | 属性名称 |
| PropertyName\_OfficePhone | 属性名称 |
| PropertyName\_QQ | 属性名称 |
| PropertyName\_IdNumber | 属性名称 |
| PropertyName\_EmployeeRank | 属性名称：员工职级 |
| PropertyName\_ProfilePhotoUrl | 属性名称 |
| PropertyName\_DepartmentName | 属性名称 |
| PropertyName\_Password | 属性名称 |
| \_Password | 用户的Password |
| PropertyName\_Mobile | 属性名称 |
| PropertyName\_Email | 属性名称 |
| PropertyName\_DingTalkAccount | 用户的DingTalkid |
| PropertyName\_DingId | 属性名称 |
| PropertyName\_WeChatUserId | 属性名称 |
| PropertyName\_Position | 属性名称 |
| PropertyName\_ExtAttr | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Organization.DomainType)

| 参数 | 说明 |
| --- | --- |
| "domainType" | 组织机构隶属于的域类型 |
| 返回值 |  |
| |  |


方法名称 : IsExternalId(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectId" | |
| 返回值 |  |
| |  |


方法名称 : Validate(System.String)

| 参数 | 说明 |
| --- | --- |
| "code" | 忽略掉'\_', '.', '-'只允许有一个'\\' |
| 返回值 |  |
| 如果验证成功，则返回true，否则返回false |  |


方法名称 : Validate(H3.Organization.IOrganizationValidator)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织结构接口，用来获得人员、OU、组等信息 |
| 返回值 |  |
| 如果合法则返回SUCCESS，否则返回错误代码 |  |


方法名称 : GetIndexableProperties(System.Boolean)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 所有课索引的字段 |  |


方法名称 : GetIndexablePropertyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 索引字段的名称 |
| 返回值 |  |
| 索引的值 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | 对象名称 |
| 返回值 |  |
| 键值对 |  |