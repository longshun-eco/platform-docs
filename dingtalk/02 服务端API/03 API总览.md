---
title: "API总览"
source: "https://open.dingtalk.com/document/development/api-overview"
category: "服务端API"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-api-overview_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-api-overview_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22钉钉开放平台提供了一整套服务端API，帮助开发者实现企业级应用的集成与定制。本文档汇总了钉钉各类服务端API接口，涵盖通讯录、考勤、OA审批、日程、消息等核心能力，支持企业内部应用和第三方企业应用等多种应用类型。

在调用钉钉服务端API前，请务必了解以下关键概念：

* **应用类型**：根据使用场景分为企业内部应用（自建应用）、第三方企业应用（ISV应用）和第三方个人应用。
* **规范版本**：钉钉API分为“新版”和“旧版”两种规范。新版API基于OpenAPI 3.0标准设计，推荐优先使用；旧版API为历史接口，部分功能仍在维护。
* **调用流程**：大多数API需先获取`access_token`作为身份凭证，再携带该凭证发起具体业务请求。

**重要**

开发者如需同时调用旧版与新版服务端API，请参考[如何调用服务端API](/document/development/how-to-call-apis)文档，了解完整的认证机制与调用流程。

## 角色权限说明

|  |  |
| --- | --- |
| 应用类型 | 权限说明 |
| 企业内部应用 | 可调用本企业范围内的所有支持API。 |
| 第三方企业应用 | 需经目标企业授权后方可调用其数据相关API。 |
| 第三方个人应用 | 仅支持基础用户级操作，不支持企业数据访问。 |

特殊限制：

* 涉及敏感信息（如通讯录、考勤）的接口需申请特殊权限包。
* 所有接口调用均需遵守《钉钉开放平台开发者协议》。

## 身份验证（免登）

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API名称** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取应用管理后台免登的用户信息](/document/orgapp/obtains-the-identity-of-an-application-administrator) | 调用本接口通过获取到的免登授权码code和获取到的应用后台免登的access\_token来换取应用管理员的身份信息。 | 新版 | 支持 | 支持 | 不支持 |
| [通过免登码获取用户信息](/document/orgapp/obtain-the-userid-of-a-user-by-using-the-log-free) | 调用本接口通过access\_token和免登接口得到的code来获取用户基本信息。 | 旧版 | 支持 | 支持 | 不支持 |

## 获取访问凭证

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取用户token](/document/orgapp/obtain-user-token) | 调用本接口获取用户token。 | 新版 | 支持 | 支持 | 支持 |
| [获取企业内部应用的accessToken](/document/orgapp/obtain-the-access_token-of-an-internal-app) | 企业内部应用调用本接口获取accessToken。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取定制应用的accessToken](/document/orgapp/obtain-the-access_token-of-the-authorized-enterprise) | 服务商可通过此接口获取授权企业的accessToken。 | 新版 | 支持 | 支持 | 不支持 |
| [创建jsapiTicket](/document/orgapp/create-a-jsapi-ticket) | 开发H5微应用时，可通过本接口获取jsapi\_ticket。 | 新版 | 支持 | 支持 | 不支持 |
| [获取微应用后台免登的accessToken](/document/orgapp/obtain-the-access_token-of-the-micro-application-background-without-log-on) | 调用本接口获取微应用后台免登的access\_token。 | 新版 | 支持 | 支持 | 不支持 |

## 通讯录管理

### 获取通讯录权限范围

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取通讯录权限范围](/document/orgapp/obtain-corpsecret-authorization-scope) | 调用通讯录相关接口前，需要添加通讯录接口权限，可通过当前接口获取通讯录权限范围。 | 旧版 | 支持 | 支持 | 不支持 |

### 用户管理

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API名称** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询离职记录列表](/document/orgapp/query-the-details-of-employees-who-have-left-office) | 调用本接口查询企业离职记录列表。 | 新版 | 支持 | 不支持 | 不支持 |
| [设置高管模式](/document/orgapp/update-executive-settings) | 调用本接口设置员工的高管模式。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取用户高管模式设置](/document/orgapp/get-user-executive-mode-settings) | 调用本接口设置员工的高管模式。 | 新版 | 支持 | 不支持 | 不支持 |
| [删除用户属性可见性设置](/document/orgapp/delete-enterprise-employee-attribute-field-visibility-settings) | 调用本接口删除企业员工属性字段可见性设置。 | 新版 | 支持 | 支持 | 不支持 |
| [获取用户属性可见性设置](/document/orgapp/pull-hidden-property-field-for-enterprise-employees) | 调用本接口获取企业员工属性字段隐藏设置。 | 新版 | 支持 | 支持 | 不支持 |
| [设置用户属性可见性](/document/orgapp/add-or-update-the-hidden-settings-of-the-employee-property) | 调用本接口新增或更新企业员工属性字段隐藏设置。 | 新版 | 支持 | 支持 | 不支持 |
| [创建用户](/document/orgapp/user-information-creation) | 调用本接口创建新用户。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新用户信息](/document/orgapp/user-information-update) | 调用本接口更新用户详情。 | 旧版 | 支持 | 不支持 | 不支持 |
| [删除用户](/document/orgapp/delete-a-user) | 调用本接口删除指定用户。 | 旧版 | 支持 | 不支持 | 不支持 |
| [查询用户详情](/document/orgapp/query-user-details) | 调用本接口根据userid获取用户详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取部门用户基础信息](/document/orgapp/queries-the-simple-information-of-a-department-user) | 调用本接口获取部门用户基础信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取部门用户userid列表](/document/orgapp/query-the-list-of-department-userids) | 调用本接口根据部门ID获取指定部门的userid列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取部门用户详情](/document/orgapp/queries-the-complete-information-of-a-department-user) | 调用本接口获取部门用户详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取员工人数](/document/orgapp/obtain-the-number-of-employees-v2) | 调用本接口获取企业员工的人数。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取未登录钉钉的员工列表](/document/orgapp/queries-the-inactive-users-or-active-users-under-an-enterprise) | 调用本接口查询指定日期内未登录钉钉的企业员工列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [根据手机号查询用户](/document/orgapp/query-users-by-phone-number) | 调用本接口根据手机号获取用户的userid。 | 旧版 | 支持 | 不支持 | 不支持 |
| [根据unionid获取用户userid](/document/orgapp/query-a-user-by-the-union-id) | 调用本接口根据unionid获取用户的userid。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取管理员列表](/document/orgapp/query-the-administrator-list) | 调用本接口获取管理员列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取管理员通讯录权限范围](/document/orgapp/query-permissions-of-the-administrator-address-book) | 调用本接口获取管理员通讯录权限范围。 | 旧版 | 支持 | 支持 | 不支持 |

### 企业账号

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [根据迁移后的dingId查询原dingId](/document/orgapp/query-the-original-dingid-based-on-the-dingid-after-migration) | 根据迁移后的dingId查询原dingId。 | 新版 | 支持 | 支持 | 不支持 |
| [根据迁移后的unionId查询原unionId](/document/orgapp/query-the-original-union-id-based-on-the-union-id) | 根据迁移后的unionId查询原unionId。 | 新版 | 支持 | 支持 | 不支持 |
| [根据原dingId查询迁移后的dingId](/document/orgapp/query-the-new-dingid-based-on-the-original-dingid) | 根据原dingId查询迁移后的dingId。 | 新版 | 支持 | 支持 | 不支持 |
| [根据原unionId查询迁移后的unionId](/document/orgapp/the-union-id-that-you-want-to-query-you-can) | 根据原unionId查询迁移后的unionId。 | 新版 | 支持 | 支持 | 不支持 |
| [启用企业账号](/document/orgapp/enable-a-dedicated-account) | 调用本接口启用指定企业账号。 | 新版 | 支持 | 不支持 | 不支持 |
| [停用企业账号](/document/orgapp/disable-an-exclusive-account) | 调用本接口停用指定的企业账号。 | 新版 | 支持 | 不支持 | 不支持 |
| [强制登出企业账号](/document/orgapp/force-logout-from-dedicated-account) | 调用本接口强制登出指定的企业账号。 | 新版 | 支持 | 不支持 | 不支持 |
| [查询企业账号状态](/document/orgapp/query-dedicated-account-status-1) | 调用本接口查询某企业账号的启用状态。 | 新版 | 支持 | 不支持 | 不支持 |
| [授权企业账号可加入多组织](/document/orgapp/authorize-a-dedicated-account-to-join-multiple-organizations) | 调用本接口授权企业账号可以加入多个组织。 | 新版 | 支持 | 不支持 | 不支持 |
| [查询企业账号拥有的组织](/document/orgapp/you-can-call-this-operation-to-query-the-organization-that) | 调用本接口用于查询企业账号在哪些企业下拥有创建者身份，并获取这些企业信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [企业账号转交主管理员（创建者）](/document/orgapp/transfer-exclusive-account-to-main-administrator-creator) | 调用本接口将本组织内某企业账号有所有权的组织，转交给另一企业账号。 | 新版 | 支持 | 不支持 | 不支持 |
| [创建SSO企业账号](/document/orgapp/create-an-sso-account) | 调用本接口创建SSO企业账号新用户。 | 旧版 | 支持 | 不支持 | 不支持 |
| [创建钉钉自建企业账号](/document/orgapp/create-dingtalk-user-created-dedicated-account) | 调用本接口创建钉钉自建企业账号新用户。 | 旧版 | 支持 | 不支持 | 不支持 |
| [邀请其他组织企业账号加入](/document/orgapp/invite-other-organization-specific-accounts-to-join) | 调用本接口邀请其他组织企业账号加入。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新企业账号用户信息](/document/orgapp/update-dedicated-accounts-information) | 调用本接口更新指定的企业账号用户信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [查询企业账号用户详情](/document/orgapp/queries-the-details-of-a-dedicated-account) | 调用本接口获取指定企业账号用户的详细信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取部门企业账号用户详情](/document/orgapp/queries-account-details) | 调用本接口获取指定部门中的用户详细信。 | 旧版 | 支持 | 支持 | 不支持 |
| [根据手机号查询企业账号用户](/document/orgapp/obtain-the-userid-of-your-mobile-phone-number) | 调用本接口根据手机号获取企业账号用户的userId。 | 旧版 | 支持 | 不支持 | 不支持 |

### 部门管理

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建部门](/document/orgapp/create-a-department-v2) | 调用本接口创建新部门。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新部门](/document/orgapp/update-a-department-v2) | 调用本接口更新部门信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [删除部门](/document/orgapp/delete-a-department-v2) | 调用本接口根据部门ID删除指定部门。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取部门详情](/document/orgapp/query-department-details0-v2) | 调用本接口根据部门ID获取指定部门详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取部门列表](/document/orgapp/obtain-the-department-list-v2) | 调用本接口获取部门列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取子部门ID列表](/document/orgapp/obtain-a-sub-department-id-list-v2) | 调用本接口获取企业部门下的所有直属子部门列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取指定部门的所有父部门列表](/document/orgapp/query-the-list-of-all-parent-departments-of-a-department) | 调用本接口获取指定部门的所有部门列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取指定用户的所有父部门列表](/document/orgapp/queries-the-list-of-all-parent-departments-of-a-user) | 调用本接口查询指定用户所属的所有父级部门。 | 旧版 | 支持 | 支持 | 不支持 |

### 角色管理

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建角色](/document/orgapp/add-role) | 调用本接口创建新角色。 | 旧版 | 支持 | 不支持 | 不支持 |
| [创建角色组](/document/orgapp/add-a-role-group) | 调用本接口创建角色组。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新角色名称](/document/orgapp/update-role) | 调用本接口更新角色名称。 | 旧版 | 支持 | 不支持 | 不支持 |
| [批量增加员工角色](/document/orgapp/add-role-information-to-employees-in-batches) | 调用本接口批量增加员工角色。 | 旧版 | 支持 | 不支持 | 不支持 |
| [删除角色](/document/orgapp/delete-role-information) | 调用本接口根据角色ID删除指定的角色。 | 旧版 | 支持 | 不支持 | 不支持 |
| [批量删除员工角色](/document/orgapp/delete-the-color-information-of-employee-corners-in-batches) | 调用本接口批量删除员工的角色。 | 旧版 | 支持 | 不支持 | 不支持 |
| [设定角色成员管理范围](/document/orgapp/update-role-member-management-department-scope) | 调用本接口设定角色成员管理范围。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取角色组列表](/document/orgapp/obtains-the-role-group-information) | 调用本接口获取角色组信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取角色列表](/document/orgapp/obtains-a-list-of-enterprise-roles) | 调用本接口获取角色列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取角色详情](/document/orgapp/queries-role-details) | 调用本接口根据角色ID获取指定角色详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取指定角色的员工列表](/document/orgapp/obtain-the-list-of-employees-of-a-role) | 调用本接口获取指定角色的员工列表。 | 旧版 | 支持 | 支持 | 不支持 |

### 外部联系人

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [添加外部联系人](/document/orgapp/add-enterprise-external-contacts) | 调用本接口添加企业外部联系人。 | 旧版 | 支持 | 不支持 | 不支持 |
| [删除外部联系人](/document/orgapp/delete-external-contact) | 调用本接口删除企业外部联系人。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新外部联系人](/document/orgapp/update-enterprise-external-contacts) | 调用本接口更新企业外部联系人。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取外部联系人列表](/document/orgapp/obtain-the-external-contact-list) | 调用本接口获取企业外部联系人列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取外部联系人标签列表](/document/orgapp/obtains-a-list-of-external-contact-tags) | 调用本接口获取企业外部联系人的标签。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取外部联系人详情](/document/orgapp/obtains-the-external-contact-details-of-an-enterprise) | 调用本接口获取企业外部联系人的详细信息。 | 旧版 | 支持 | 支持 | 不支持 |

### 企业管理

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **描述** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取企业邀请信息](/document/orgapp/obtain-invitation-information) | 调用本接口获取企业邀请信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取企业最新钉钉指数信息](/document/orgapp/queries-the-latest-dingtalk-index-information) | 调用本接口获取企业最新钉钉指数信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取企业认证信息](/document/orgapp/obtain-enterprise-authentication-information) | 调用本接口获取企业认证信息。 | 新版 | 支持 | 支持 | 不支持 |

### 通讯录设置

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| API | 说明 | 规范版本 | 企业内部应用 | 第三方企业应用 | 第三方个人应用 |
| [获取通讯录隐藏设置](/document/orgapp/obtains-the-hide-settings-of-the-address-book) | 调用本接口批量获取通讯录隐藏的设置列表。 | 新版 | 支持 | 不支持 | 不支持 |
| [删除通讯录隐藏设置](/document/orgapp/delete-hide-settings) | 调用本接口删除通讯录隐藏设置。 | 新版 | 支持 | 不支持 | 不支持 |
| [更新通讯录隐藏设置](/document/orgapp/update-address-book-hide-settings) | 调用本接口新增或更新通讯录隐藏设置。 | 新版 | 支持 | 不支持 | 不支持 |
| [设置部门可见性优先级](/document/orgapp/set-address-book-visibility-sub-department-settings-to-take-precedence) | 调用本接口获取企业用户通讯录中的个人信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [新增或修改限制查看通讯录设置](/document/orgapp/add-or-modify-visibility-settings-for-address-book-restrictions) | 调用本接口新增或修改限制查看通讯录设置。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取限制查看通讯录设置列表](/document/orgapp/gets-a-list-of-address-book-limit-visibility-settings) | 调用本接口获取限制查看通讯录设置信息列表。 | 新版 | 支持 | 不支持 | 不支持 |
| [删除限制查看通讯录设置](/document/orgapp/delete-visible-restrictions) | 调用本接口删除限制查看通讯录设置。 | 新版 | 支持 | 不支持 | 不支持 |

### 行业通讯录

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取部门详情](/document/orgapp/industry-address-book-api-for-obtaining-department-information) | 调用本接口根据部门ID获取部门详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取部门下人员列表](/document/orgapp/obtains-the-list-of-people-under-a-department) | 调用本接口获取部门下的人员列表信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取部门列表](/document/orgapp/obtains-a-list-of-industry-departments) | 调用本接口根据部门ID获取部门列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取部门用户详情](/document/orgapp/queries-department-user-details) | 调用本接口获取部门用户详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取企业信息](/document/orgapp/obtain-enterprise-information) | 调用本接口获取行业通讯录的企业信息。 | 旧版 | 支持 | 支持 | 不支持 |

### 获取用户通讯录个人信息

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取用户通讯录个人信息](/document/orgapp/dingtalk-retrieve-user-information) | 调用本接口获取企业用户通讯录中的个人信息。 | 新版 | 支持 | 支持 | 支持 |

## **上下游组织**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建上下游组织](/document/orgapp/create-a-cooperation-space) | 调用本接口创建上下游组织。 | 新版 | 支持 | 支持 | 支持 |
| [获取上下游组织的邀请信息](/document/orgapp/obtain-the-invitation-information-of-a-cooperation-space) | 调用本接口获取企业已经加入的上下游组织信息或获取企业已经加入的上下游组织信息。 | 新版 | 支持 | 支持 | 支持 |
| [更新分支组织在主干组织内的属性信息](/document/orgapp/update-properties-of-branches-in-alibaba-group-1) | 调用本接口更新伙伴组织在上下游组织内内的属性信息。 | 新版 | 支持 | 支持 | 不支持 |
| [设置伙伴组织在上下游组织内的可见范围](/document/orgapp/set-the-visible-range-of-the-branch-in-the-group-1) | 调用本接口设置伙伴组织在上下游组织内的可见范围。 | 新版 | 支持 | 支持 | 不支持 |
| [解除关联组织](/document/orgapp/disassociate-upstream-and-downstream-organizations) | 调用本接口用于解除关联组织关系。 | 新版 | 支持 | 支持 | 不支持 |
| [批量通过伙伴组织的加入申请](/document/orgapp/apply-for-batch-addition-through-upstream-and-downstream-organizations) | 调用本接口批量通过伙伴组织加入上下游组织申请。 | 新版 | 支持 | 支持 | 不支持 |
| [获取已加入或正在申请加入上下游组织的组织和个人信息](/document/orgapp/obtains-the-information-about-how-to-join-or-apply-to) | 调用本接口通过合作空间组织ID获取加入或申请加入合作空间的组织和个人信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取企业已经加入的或申请加入中的上下游组织的信息](/document/orgapp/obtains-information-about-the-workspaces-that-the-enterprise-has-joined) | 调用本接口获取企业已经加入或申请加入的合作空间的信息。 | 旧版 | 支持 | 支持 | 不支持 |

## **上下级组织**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [设置分支组织在主干组织内的可见范围](/document/orgapp/sets-the-visible-range-of-branch-organizations-within-the-group) | 调用本接口设置分支组织在主干组织内的可见范围，也可以设置分支组织在主干组织内可以被哪些部门可见。 | 新版 | 支持 | 支持 | 不支持 |
| [更新分支组织在主干组织内的属性信息](/document/orgapp/updates-the-property-information-of-a-branch-organization-in-a) | 调用本接口更新分支组织在主干组织内内的属性信息。 | 新版 | 支持 | 支持 | 不支持 |
| [解除关联组织](/document/orgapp/disassociate-an-organization) | 调用本接口用于解除关联组织关系。 | 新版 | 支持 | 支持 | 不支持 |
| [批量通过伙伴组织的加入申请](/document/orgapp/batch-through-the-application-of-partner-organizations-to-join-contact) | 调用本接口批量通过伙伴组织加入上下级组织申请。 | 新版 | 支持 | 支持 | 不支持 |
| [获取主干组织列表](/document/orgapp/obtain-backbone-organization-list) | 调用本接口获取主干组织列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取分支组织列表](/document/orgapp/obtains-the-branch-organization-list) | 调用本接口获取分支组织列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取上下级组织分支授权的数据](/document/orgapp/data-authorized-by-a-branch-of-an-associated-organization) | 调用本接口获取关联组织分支授权的数据。 | 旧版 | 支持 | 不支持 | 不支持 |

## **服务窗**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [批量发送服务窗消息](/document/orgapp/batch-sending-of-service-window-messages) | 调用本接口向服务窗的一批粉丝用户发送消息。 | 旧版 | 支持 | 支持 | 不支持 |
| [发送服务窗单人消息](/document/orgapp/sends-a-single-message-from-the-service-window) | 调用本接口向指定的用户发送服务窗消息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业下服务窗列表](/document/orgapp/queries-the-list-of-services-under-an-enterprise) | 调用本接口获取企业下创建的服务窗列表。 | 新版 | 支持 | 不支持 | 不支持 |
| [批量获取关注服务窗用户信息](/document/orgapp/obtains-the-follower-information-from-the-service-window) | 调用本接口分页获取关注服务窗用户信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取关注服务窗用户信息](/document/orgapp/queries-the-follower-information-of-the-service-window) | 调用本接口获取关注服务窗用户的基本信息。 | 新版 | 支持 | 不支持 | 不支持 |

## **会话管理**

### **会话1.0**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取群会话的OpenConversationId](/document/orgapp/obtain-group-openconversationid) | 调用本接口通过chatId查询OpenConversationId。 | 新版 | 支持 | 不支持 | 不支持 |
| [批量设置企业群管理员](/document/orgapp/batch-setup-group-administrator) | 调用本接口可以批量设置企业群内用户为管理员身份， 也可以批量取消企业群内用户的管理员身份。 | 新版 | 支持 | 不支持 | 不支持 |
| [创建群会话](/document/orgapp/create-group-session) | 调用本接口创建群会话。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取群会话信息](/document/orgapp/obtain-a-group-session) | 调用本接口获取群设置和成员信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [修改群会话](/document/orgapp/modify-a-group-session) | 调用本接口修改群会话。 | 旧版 | 支持 | 不支持 | 不支持 |
| [设置群管理员](/document/orgapp/set-chat-admin) | 调用本接口设置群管理员。 | 旧版 | 支持 | 不支持 | 不支持 |
| [设置禁止群成员私聊](/document/orgapp/set-private-chat) | 调用本接口设置群成员之间是否可以添加好友和私聊。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取入群二维码链接](/document/orgapp/obtain-a-qr-code-link) | 调用本接口获取群入群二维码邀请链接。 | 旧版 | 支持 | 不支持 | 不支持 |
| [设置群成员昵称](/document/orgapp/set-a-group-nickname) | 调用本接口设置群成员在群中的昵称。 | 旧版 | 支持 | 不支持 | 不支持 |

### **会话2.0**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建群](/document/orgapp/create-a-scene-group-v2) | 调用本接口根据群模板ID创建群。 | 旧版 | 支持 | 支持 | 不支持 |
| [更新群](/document/orgapp/scene-group-update) | 调用本接口更新群配置。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询群信息](/document/orgapp/queries-the-basic-information-of-a-scenario-group) | 调用本接口根据群ID查询场景群的基本信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [新增群成员](/document/orgapp/add-people-to-scene-group) | 调用本接口新增群成员。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除群成员](/document/orgapp/scene-group-delete) | 调用本接口删除群成员。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询群成员](/document/orgapp/query-group-members) | 调用本接口根据群ID查询群成员列表。 | 新版 | 支持 | 支持 | 不支持 |
| [设置群成员禁言状态](/document/orgapp/set-group-members-access-control) | 调用本接口设置场景群内的群成员禁言状态，可设置指定群成员禁言或解除禁言。 | 新版 | 支持 | 支持 | 不支持 |
| [查询群禁言状态](/document/orgapp/query-group-silence-status) | 通过本接口查询群和群内成员的禁言状态。 | 新版 | 支持 | 支持 | 不支持 |
| [更新群成员的群昵称](/document/orgapp/update-group-nicknames) | 调用本接口更新场景群群成员的群昵称。 | 新版 | 支持 | 支持 | 不支持 |
| [更新群管理员](/document/orgapp/update-group-administrators) | 调用本接口更新群的群管理员。 | 新版 | 支持 | 支持 | 不支持 |
| [查询群简要信息](/document/orgapp/query-group-information) | 调用本接口根据群ID查询群的简要信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询群内群模板机器人](/document/orgapp/search-group-scene-template-robot) | 调用本接口查询群内群模板机器人信息。 | 新版 | 支持 | 支持 | 不支持 |
| [启用群模板](/document/orgapp/enable-a-group-template) | 调用本接口根据群模板ID启用群模板。 | 旧版 | 支持 | 支持 | 不支持 |
| [停用群模板](/document/orgapp/disable-a-group-template) | 调用本接口根据群模板ID停用群模板。 | 旧版 | 支持 | 支持 | 不支持 |
| [创建并开启互动卡片吊顶](/document/orgapp/create-and-open-an-interactive-card-ceiling) | 调用本接口创建并开启会话中的互动卡片吊顶。 | 新版 | 支持 | 支持 | 不支持 |
| [关闭互动卡片吊顶](/document/orgapp/close-interactive-card-ceiling) | 调用本接口关闭会话中的互动卡片吊顶。 | 新版 | 支持 | 支持 | 不支持 |
| [发送群助手消息](/document/orgapp/send-group-helper-message) | 调用本接口在场景群中通过群助手发送消息。 | 旧版 | 支持 | 支持 | 不支持 |

## **消息**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [发送工作通知](/document/orgapp/asynchronous-sending-of-enterprise-session-messages) | 发送工作通知消息。 | 旧版 | 支持 | 支持 | 不支持 |
| [更新工作通知状态栏](/document/orgapp/update-work-notification-status-bar) | 更新OA工作通知消息的状态。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取工作通知消息的发送进度](/document/orgapp/obtain-the-sending-progress-of-asynchronous-sending-of-enterprise-session) | 获取工作通知消息的发送进度。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取工作通知消息的发送结果](/document/orgapp/gets-the-result-of-sending-messages-asynchronously-to-the-enterprise) | 查询工作通知消息的发送结果。 | 旧版 | 支持 | 支持 | 不支持 |
| [撤回工作通知消息](/document/orgapp/notification-of-work-withdrawal) | 撤回工作消息通知。 | 旧版 | 支持 | 支持 | 不支持 |

## **机器人**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [批量发送单聊消息](https://open.dingtalk.com/document/orgapp/chatbots-send-one-on-one-chat-messages-in-batches) | 调用本接口通过机器人批量发送单聊消息。 | 新版 | 支持 | 支持 | 不支持 |
| [机器人发送群聊消息](https://open.dingtalk.com/document/orgapp/the-robot-sends-a-group-message) | 调用本接口通过机器人发送群聊消息。 | 新版 | 支持 | 支持 | 不支持 |
| [机器人发送互动卡片（普通版）](https://open.dingtalk.com/document/orgapp/robots-send-interactive-cards) | 调用本接口通过机器人发送普通版互动卡片消息。 | 新版 | 支持 | 支持 | 不支持 |
| [更新机器人发送互动卡片（普通版）](https://open.dingtalk.com/document/orgapp/update-the-robot-to-send-interactive-cards) | 调用本接口通过机器人更新普通版互动卡片消息。 | 新版 | 支持 | 支持 | 不支持 |
| [注册互动卡片回调地址](https://open.dingtalk.com/document/orgapp/registration-card-interaction-callback-address-1) | 调用本接口注册互动卡片的回调地址。注册后，开发者后台系统可感知到用户对卡片的操作。 | 旧版 | 支持 | 支持 | 不支持 |
| [发送钉钉互动卡片](https://open.dingtalk.com/document/orgapp/send-interactive-dynamic-cards-1) | 调用本接口通过机器人发送钉钉互动卡片消息。 | 新版 | 支持 | 支持 | 不支持 |
| [更新钉钉互动卡片](https://open.dingtalk.com/document/orgapp/update-dingtalk-interactive-cards-1) | 调用本接口通过机器人更新钉钉互动卡片消息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询机器人单聊消息已读状态](https://open.dingtalk.com/document/orgapp/chatbot-batch-query-the-read-status-of-messages) | 调用本接口获取各个消息接收者是否已读消息情况。 | 新版 | 支持 | 支持 | 不支持 |
| [查询机器人群聊消息已读状态](https://open.dingtalk.com/document/orgapp/chatbot-queries-the-read-status-of-a-message) | 调用本接口获取机器人消息发送状态、消息已读成员userId等信息。 | 新版 | 支持 | 支持 | 不支持 |
| [批量撤回单聊消息](https://open.dingtalk.com/document/orgapp/batch-message-recall-chat) | 调用本接口能批量撤回机器人发送的单聊消息。 | 新版 | 支持 | 支持 | 不支持 |
| [企业机器人撤回内部群消息](https://open.dingtalk.com/document/orgapp/enterprise-chatbot-withdraws-internal-group-messages) | 调用本接口可用于实现企业机器人撤回内部群消息。 | 新版 | 支持 | 支持 | 不支持 |

## **钉钉客联**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建钉钉客联账号关联关系](/document/orgapp/create-bc-account-association) | 创建钉外用户账号，并建立与钉内用户的账号关联关系。 | 新版 | 支持 | 支持 | 不支持 |
| [创建普通群或跨钉两人群](/document/orgapp/create-group-sessions) | 创建钉钉客联互通群，群类型为普通群或跨钉两人群。 | 新版 | 支持 | 支持 | 不支持 |
| [创建钉外两人群](/document/orgapp/create-two-people-outside-the-nail) | 创建钉外两人群。 | 新版 | 支持 | 支持 | 不支持 |
| [创建店铺群](/document/orgapp/create-a-store-group) | 创建店铺群。 | 新版 | 支持 | 支持 | 不支持 |
| [获取钉钉客联群会话地址](/document/orgapp/get-the-dingtalk-guest-group-session-address) | 获取钉钉客联群会话地址，钉外用户可通过该地址进入对应群内。 | 新版 | 支持 | 支持 | 不支持 |
| [添加互通群成员](/document/orgapp/add-a-group-member-1) | 向互通群内添加群成员。 | 新版 | 支持 | 支持 | 不支持 |
| [查询互通群成员列表](/document/orgapp/queries-the-group-member-list) | 查询互通群成员列表，包括普通群、跨钉两人群、钉外两人群和店铺群。 | 新版 | 支持 | 支持 | 不支持 |
| [移除互通群成员](/document/orgapp/remove-group-members) | 移除互通群成员。 | 新版 | 支持 | 支持 | 不支持 |
| [修改互通群头像](/document/orgapp/modify-the-avatar-of-a-communication-group) | 修改互通群头像，包括普通群、跨钉两人群、钉外两人群和商铺群。 | 新版 | 支持 | 支持 | 不支持 |
| [修改互通群名称](/document/orgapp/modify-the-group-name) | 修改群名称，包括普通群、跨钉两人群、钉外两人群和店铺群。 | 新版 | 支持 | 支持 | 不支持 |
| [更换互通群群主](/document/orgapp/change-group-owner) | 更换互通群的群主。 | 新版 | 支持 | 支持 | 不支持 |
| [钉外用户向钉内用户或互通群发送消息](/document/orgapp/send-c2b-messages) | 实现钉外用户向钉内用户或互通群发送消息。 | 新版 | 支持 | 支持 | 不支持 |
| [钉内用户向互通群或钉外用户发送消息](/document/orgapp/send-b2c-messages) | 实现钉内用户给钉外用户或者互通群发送消息。 | 新版 | 支持 | 支持 | 不支持 |
| [互通群机器人发送群消息](/document/orgapp/group-robots-send-messages) | 通过互通群内机器人向群内发送消息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询钉外用户未读消息的数量](/document/orgapp/querying-the-number-of-unread-messages-of-the-user) | 查询钉外用户未读消息的数量。 | 新版 | 支持 | 支持 | 不支持 |
| [批量查询跨钉两人群列表](/document/orgapp/queries-the-session-information-of-two-population-groups) | 根据群成员批量查询跨钉两人群列表。 | 新版 | 支持 | 支持 | 不支持 |
| [解散互通群](/document/orgapp/disband-bc-interconnection-group) | 解散互通群，包括普通群、跨钉两人群、钉外两人群和店铺群。 | 新版 | 支持 | 支持 | 不支持 |

## 考勤

### **考勤组管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询考勤写操作权限](/document/orgapp/attendance-writing-operation-is-brand-new-query) | 用于查询企业员工在考勤组内的操作权限。 | 新版 | 支持 | 支持 | 不支持 |
| [创建考勤组](/document/orgapp/attendance-group-write) | 调用本接口创建考勤组。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新考勤组](/document/orgapp/attendance-group-update-interface) | 调用本接口根据考勤组id更新考勤组信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [删除考勤组](/document/orgapp/delete-attendance-group) | 调用本接口批量删除考勤组。 | 旧版 | 支持 | 不支持 | 不支持 |
| [搜索考勤组摘要](/document/orgapp/attendance-group-search) | 调用本接口按考勤组名称模糊搜索，获取考勤组摘要信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取考勤组详情](/document/orgapp/query-a-single-attendance-group) | 调用本接口根据考勤组ID获取考勤组详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [根据groupKey查询考勤组信息](/document/orgapp/queries-attendance-group-information-by-id) | 调用本接口根据考勤组id查询考勤组信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [groupKey转换为groupId](/document/orgapp/convert-groupkey-to-groupid) | 调用本接口将考勤组的groupKey转换为groupId。 | 旧版 | 支持 | 支持 | 不支持 |
| [groupId转换为groupKey](/document/orgapp/groupid-to-groupkey) | 调用本接口将考勤组的groupId转换为groupKey。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量获取考勤组摘要](/document/orgapp/batch-query-of-simple-information-of-the-attendance-group) | 调用本接口分页获取企业内所有考勤组摘要信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量获取考勤组详情](/document/orgapp/batch-obtain-attendance-group-details) | 调用本接口查询所有的考勤组详情信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取用户考勤组](/document/orgapp/queries-a-user-attendance-group) | 调用本接口获取员工的考勤组信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [批量新增参与考勤人员](/document/orgapp/batch-add-employees-under-the-attendance-group) | 调用本接口在指定的考勤组下批量新增考勤组成员。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新参与考勤人员](/document/orgapp/attendance-group-member-update) | 调用本接口更新考勤组成员，支持新增或删除人员、部门、无需考勤人员。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取参与考勤人员](/document/orgapp/batch-query-of-attendance-group-members) | 调用本接口通过操作人的userid和考勤组id获取当前考勤组下的成员信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取参与考勤人员的userid](/document/orgapp/query-attendance-group-personnel-information-in-batches) | 调用本接口分页获取某个考勤组下的所有员工的userId。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量删除参与考勤人员](/document/orgapp/batch-delete-employees-under-the-attendance-group) | 调用本接口批量删除指定考勤组下的考勤组成员。 | 旧版 | 支持 | 不支持 | 不支持 |
| [查询参与考勤人员列表](/document/orgapp/batch-query-of-employees-in-the-attendance-group) | 调用本接口查询指定考勤组下的员工列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [校验用户是否在当前考勤组](/document/orgapp/query-members-by-id) | 调用本接口校验某个部门或者员工是否属于某个考勤组，返回值为属于这个考勤组的部门ID或者员工ID。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量新增Wi-Fi信息](/document/orgapp/batch-add-wifi-under-attendance-group) | 调用本接口为指定考勤组批量新增wifi信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [批量查询Wi-Fi信息](/document/orgapp/batch-query-wifi-under-attendance-group) | 调用本接口批量查询指定考勤组下的wifi列表信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [批量移除Wi-Fi信息](/document/orgapp/batch-remove-wifi-under-attendance-group) | 调用本接口批量移除指定考勤组的wifi信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [批量新增地点](/document/orgapp/atch-add-position-under-attendance-group) | 调用本接口在指定考勤组下批量新增position。 | 旧版 | 支持 | 不支持 | 不支持 |
| [批量查询地点](/document/orgapp/batch-query-position-under-attendance-group) | 调用本接口批量查询指定考勤组下的position列表信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [批量删除地点](/document/orgapp/delete-position-in-batches-under-the-attendance-group) | 调用本接口在指定考勤组下批量删除position。 | 旧版 | 支持 | 不支持 | 不支持 |

### **考勤打卡**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取打卡结果](/document/orgapp/open-attendance-clock-in-data) | 调用本接口返回企业内员工的实际打卡结果。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取打卡详情](/document/orgapp/attendance-clock-in-record-is-open) | 调用本接口返回企业内员工的实际打卡详情。 | 旧版 | 支持 | 支持 | 不支持 |

### **考勤班次**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建班次](/document/orgapp/create-modify-shifts) | 调用本接口创建钉钉考勤班次。 | 旧版 | 支持 | 不支持 | 不支持 |
| [删除班次](/document/orgapp/delete-shift) | 调用本接口根据班次ID删除考勤班次。 | 旧版 | 支持 | 不支持 | 不支持 |
| [按名称搜索班次](/document/orgapp/search-shifts-by-rank) | 调用本接口根据名称模糊搜索班次，返回班次名称和ID信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取班次摘要信息](/document/orgapp/enterprise-shift-query-in-batches) | 调用本接口查询所有的班次信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取班次详情](/document/orgapp/shift-query) | 调用本接口根据班次ID查询班次的详细信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询历史班次](/document/orgapp/query-history-shifts) | 调用本接口根据班次ID和version查询历史班次信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [修改打卡时段设置](/document/orgapp/modify-card-settings) | 调用本接口修改考勤班次卡点的设置信息。 | 旧版 | 支持 | 不支持 | 不支持 |

### **考勤排班**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询成员排班信息](/document/orgapp/query-scheduling-for-a-day) | 调用本接口查询某人在某工作日的排班信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量查询人员排班信息](/document/orgapp/query-batch-scheduling-information) | 调用本接口批量查询员工在工作日内的排班信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [排班制考勤组排班](/document/orgapp/scheduling-system-attendance-group-scheduling) | 调用此接口给排班制考勤组成员进行排班。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询排班打卡结果](/document/orgapp/query-the-results-of-a-batch-of-tasks) | 调用本接口查询排班的打卡结果，打卡结果包含打卡时间、迟到、早退、内勤及外勤等信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询企业考勤排班详情](/document/orgapp/interface-for-daily-full-query-of-attendance-scheduling-information) | 调用本接口查询某天的考勤排班信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [批量查询成员排班概要信息](/document/orgapp/query-scheduling-summary-information) | 调用本接口查询用户在某个时间段内的排班概要信息。 | 旧版 | 支持 | 不支持 | 不支持 |

### **考勤规则**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [分页获取加班规则列表](/document/orgapp/retrieve-a-list-of-overtime-rules-by-page) | 调用本接口分页获取考勤打卡中设置的加班规则列表。 | 新版 | 支持 | 支持 | 不支持 |
| [分页获取补卡规则列表](/document/orgapp/retrieve-a-list-of-replenishment-rules-by-page) | 调用本接口分页获取考勤打卡中设置的补卡规则列表。 | 新版 | 支持 | 支持 | 不支持 |
| [批量获取加班规则设置](/document/orgapp/batch-retrieve-overtime-rules) | 调用本接口用于根据多个加班规则ID，批量获取加班规则设置详情。 | 新版 | 支持 | 支持 | 不支持 |

### **考勤统计**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询用户某段时间内是否处于封账状态](/document/orgapp/checks-whether-a-user-has-blocked-accounts-within-a-specified) | 调用本接口查询员工一段时间内是否处于封账状态，如果处于封账状态，不能发起审批、排班、换班等操作。 | 新版 | 支持 | 支持 | 不支持 |
| [查询是否启用智能统计报表](/document/orgapp/determine-whether-to-enable-attendance-intelligent-report) | 调用本接口判断企业是否开启了考勤智能报表，如果企业未启用智能报表，无法调用统计报表其他的接口。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取用户考勤数据](/document/orgapp/obtain-the-attendance-update-data) | 调用本接口获取指定用户当天的考勤数据，包括打卡流水记录、打卡结果和审批列表等。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取报表假期数据](/document/orgapp/obtains-the-holiday-data-from-the-smart-attendance-report) | 调用本接口根据假期名称和用户ID获取钉钉智能考勤报表的假期数据。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取考勤报表列定义](/document/orgapp/queries-the-enterprise-attendance-report-column) | 调用本接口获取企业智能考勤报表中的列信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取考勤报表列值](/document/orgapp/queries-the-column-value-of-the-attendance-report) | 调用本接口用于获取钉钉智能考勤报表的列值数据。 | 旧版 | 支持 | 支持 | 不支持 |

### **考勤机管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [根据设备ID获取员工信息](/document/orgapp/obtain-information-about-employees-based-on-device-ids) | 调用本接口根据考勤机设备ID查询这台考勤机设备上的员工信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询考勤机信息](/document/orgapp/query-attendance-machine-information) | 调用本接口根据考勤机设备ID查询这台考勤机的相关信息。 | 新版 | 支持 | 支持 | 不支持 |
| [变更智能考勤机员工](/document/orgapp/change-intelligent-attendance-machine-staff) | 调用本接口变更智能考勤机员工。 | 新版 | 支持 | 支持 | 不支持 |
| [查询员工智能考勤机列表](/document/orgapp/query-the-list-of-employee-intelligent-attendance-machines) | 调用本接口查询员工智能考勤机列表。 | 旧版 | 支持 | 不支持 | 不支持 |

### **假期审批**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [通知审批通过](/document/orgapp/notice-of-approval) | 调用本接口通知审批通过，支持加班、请假、外出和出差类型。 | 旧版 | 支持 | 支持 | 不支持 |
| [通知审批撤销](/document/orgapp/notify-the-attendance-to-modify-the-punch-result-when-the) | 调用本接口通知审批撤销，支持加班、请假、外出、出差和补卡类型。 | 旧版 | 支持 | 支持 | 不支持 |
| [通知补卡通过](/document/orgapp/make-up-the-card-after-approval) | 调用本接口通知考勤补卡通过。 | 旧版 | 支持 | 支持 | 不支持 |
| [通知换班通过](/document/orgapp/shift-change-operation-after-approval) | 通过本接口换班审批通过后，通知考勤执行换班动作，可以和自己换班，也可以和别人换班。 | 旧版 | 支持 | 支持 | 不支持 |
| [预计算时长](/document/orgapp/calculate-duration-based-on-attendance-scheduling) | 调用本接口根据考勤系统的排班情况，预计算员工加班、出差及请假的时长信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [计算请假时长](/document/orgapp/calculate-leave-duration) | 调用本接口获取自动根据排班规则统计出每个员工的请假时长。 | 旧版 | 不支持 | 支持 | 不支持 |
| [查询请假状态](/document/orgapp/query-status) | 调用本接口查询指定企业下指定用户在指定时间段内的请假状态。 | 旧版 | 支持 | 不支持 | 不支持 |

### **假期管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [添加假期规则](/document/orgapp/add-holiday-rules) | 调用本接口新建一个假期规则。 | 新版 | 支持 | 支持 | 不支持 |
| [更新假期规则](/document/orgapp/update-holiday-rules) | 调用本接口更新指定假期的相关规则。 | 新版 | 支持 | 支持 | 不支持 |
| [添加假期规则](/document/orgapp/holiday-type-added) | 调用本接口新建一个假期规则。 | 旧版 | 支持 | 支持 | 不支持 |
| [更新假期规则](/document/orgapp/holiday-type-update) | 调用本接口更新指定假期的相关规则。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除假期规则](/document/orgapp/api-for-deleting-holiday-types) | 调用本接口删除指定的假期规则。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询假期规则列表](/document/orgapp/holiday-type-query) | 调用本接口查询企业内的假期规则列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [初始化假期余额](/document/orgapp/initialize-holiday-balance) | 调用本接口批量初始化假期余额。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询假期余额](/document/orgapp/query-holiday-balance) | 调用本接口根据企业或员工分页获取假期余额信息，每次返回50条数据。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量更新假期余额](/document/orgapp/bulk-update-holiday-balance) | 调用本接口批量更新假期余额信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量查询员工假期余额变更记录](/document/orgapp/batch-query-employee-leave-balance-change-record) | 调用本接口跟进员工分页获取假期余额记录信息。 | 新版 | 支持 | 支持 | 不支持 |

## 智能人事

### **职位管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取企业职位列表](/document/orgapp/obtain-enterprise-position-information) | 用于根据特定条件分页查询企业的职位相关信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取企业职级列表](/document/orgapp/obtain-enterprise-rank-information) | 用于分页查询企业的职级相关信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取企业职务列表](/document/orgapp/obtain-enterprise-title-information) | 用于分页查询企业的职务相关信息。 | 新版 | 支持 | 不支持 | 不支持 |

### **花名册**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取花名册字段组详情](/document/orgapp/get-roster-field-group-details) | 调用本接口查询花名册的员工档案信息中有权限的字段列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取员工花名册字段信息](/document/orgapp/intelligent-personnel-obtain-employee-roster-information) | 调用本接口查询员工花名册指定字段的信息，支持明细分组字段。 | 旧版 | 支持 | 支持 | 不支持 |
| [更新员工花名册信息](/document/orgapp/intelligent-personnel-update-employee-file-information) | 调用本接口更新员工档案信息，支持明细分组。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取花名册元数据](/document/orgapp/intelligent-personnel-roster-metadata-query) | 调用本接口获取员工花名册的元数据，包括花名册分组、字段等。 | 旧版 | 支持 | 支持 | 不支持 |

### **员工管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取离职员工列表](/document/orgapp/obtain-the-list-of-employees-who-have-left) | 查询企业离职员工userId列表。 | 新版 | 支持 | 支持 | 不支持 |
| [批量获取员工离职信息](/document/orgapp/obtain-resignation-information-of-employees-new-version) | 根据用户userId，批量查询员工的离职信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取待入职员工列表](/document/orgapp/intelligent-personnel-query-the-list-of-employees-to-be-hired) | 调用本接口查询企业待入职员工userId列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取在职员工列表](/document/orgapp/intelligent-personnel-query-the-list-of-on-the-job-employees-of-the) | 调用本接口查询企业在职员工userId列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [修改已离职员工信息](/document/orgapp/modify-resigned-employee-information) | 调用本接口修改已离职员工信息。 | 新版 | 支持 | 不支持 | 不支持 |

### **员工关系**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [智能人事员工调岗](/document/orgapp/intelligent-personnel-staff-transfer) | 智能人事员工调岗，支持以下内容调整，如员工部门列表、主部门、职务、职位和职级。 | 新版 | 支持 | 不支持 | 不支持 |
| [添加企业待入职员工](/document/orgapp/add-employees-to-be-hired-through-intelligent-personnel) | 调用本接口添加企业待入职员工。 | 旧版 | 支持 | 支持 | 不支持 |

## OA审批

### **官方OA审批**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建或更新审批表单模板](/document/orgapp/create-an-approval-form-template) | 调用本接口创建或更新一个OA审批的流程表单模板。 | 新版 | 支持 | 支持 | 不支持 |
| [获取表单 schema](/document/orgapp/obtain-the-form-schema) | 调用本接口，通过 processCode，获取对应表单的 schema 信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取审批单流程中的节点信息](/document/orgapp/approval-process-prediction) | 调用本接口获取审批单流程中的节点信息。 | 新版 | 支持 | 支持 | 不支持 |
| [发起审批实例](/document/orgapp/create-an-approval-instance) | 调用本接口用于发起OA审批实例。 | 新版 | 支持 | 支持 | 不支持 |
| [获取单个审批实例详情](/document/orgapp/obtains-the-details-of-a-single-approval-instance-pop) | 调用本接口根据审批实例ID，获取审批实例详情。 | 新版 | 支持 | 支持 | 不支持 |
| [转交OA审批任务](/document/orgapp/transfer-the-oa-approval-task) | 调用本接口转交OA审批任务。 | 新版 | 支持 | 支持 | 不支持 |
| [获取审批钉盘空间信息](/document/orgapp/obtains-the-information-about-approval-nail-disk) | 调用本接口获取审批钉盘空间的ID并授予当前用户上传附件的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [添加审批评论](/document/orgapp/add-an-approval-comment-pop) | 调用本接口对审批实例添加评论。 | 新版 | 支持 | 不支持 | 不支持 |
| [同意或拒绝审批任务](/document/orgapp/approve-or-reject-the-approval-task) | 调用本接口根据指定模板ID、审批实例ID、任务节点ID和操作人userId，对单个审批任务进行处理。 | 新版 | 支持 | 不支持 | 不支持 |
| [撤销审批实例](/document/orgapp/revoke-an-approval-instance) | 调用本接口，撤销发起的审批实例。 | 新版 | 支持 | 不支持 | 不支持 |
| [授权预览审批附件](/document/orgapp/preview-authorization-attachment-pop) | 调用本接口，授权预览审批附件。 | 新版 | 支持 | 支持 | 不支持 |
| [授权下载审批钉盘文件](/document/orgapp/download-the-approval-nail-file) | 调用本接口，根据钉盘空间spaceId和文件fileId对钉盘文件进行授权审批钉盘空间下载权限。 | 新版 | 支持 | 不支持 | 不支持 |
| [下载审批附件](/document/orgapp/download-an-approval-attachment) | 调用本接口获取审批文件下载授权，并且生成下载链接。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取用户待审批数量](/document/orgapp/queries-the-number-of-requests-to-be-approved-by-users) | 调用本接口，根据用户的userId获取该用户待处理的审批数量。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取审批实例ID列表](/document/orgapp/obtain-an-approval-list-of-instance-ids) | 调用本接口，获取权限范围内的相关部门审批实例ID列表。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取指定用户可见的审批表单列表](/document/orgapp/obtains-a-list-of-approval-forms-visible-to-the-specified) | 调用本接口，可根据员工的userId分页获取该用户可见的审批表单列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取当前企业所有可管理的表单](/document/orgapp/get-all-manageable-forms-for-the-current-enterprise) | 调用本接口，获取用户在当前企业所有可管理的审批表单。 | 新版 | 支持 | 不支持 | 不支持 |

**自有OA审批**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建或更新审批模板](/document/orgapp/save-approval-template) | 调用本接口创建或更新审批模板。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取模板code](/document/orgapp/obtains-the-template-code-based-on-the-template-name) | 调用本接口根据模板名称查询process\_code。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除模板](/document/orgapp/delete-a-template) | 调用本接口删除为企业创建的审批模板，同时删除该模板下创建的实例和待办任务。 | 旧版 | 支持 | 支持 | 不支持 |
| [创建实例](/document/orgapp/initiate-an-approval-process-without-a-process) | 调用本接口创建不带流程的审批实例。 | 旧版 | 支持 | 支持 | 不支持 |
| [更新实例状态](/document/orgapp/to-do-instance-status) | 调用本接口更新实例状态。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量更新实例状态](/document/orgapp/update-the-status-of-multiple-instances-at-a-time) | 调用本接口批量更新实例状态。 | 旧版 | 支持 | 支持 | 不支持 |
| [创建待办事项](/document/orgapp/create-a-to-do-task) | 调用本接口把待办事项的审批节点信息同步到钉钉待办。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询待办列表](/document/orgapp/query-a-user-s-to-do-items) | 调用本接口查询用户待办任务。 | 旧版 | 支持 | 支持 | 不支持 |
| [更新待办状态](/document/orgapp/update-to-do-task-status) | 调用本接口更新待办任务的状态。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量取消待办](/document/orgapp/cancel-multiple-tasks) | 调用本接口实现在或签等场景下，批量将正在运行中的待办事项设置为CANCELED。 | 旧版 | 支持 | 支持 | 不支持 |
| [创建或更新审批模板](/document/orgapp/create-or-update-approval-templates-new) | 创建或更新审批模板。 | 新版 | 支持 | 支持 | 不支持 |
| [获取模板code](/document/orgapp/obtain-the-template-code) | 根据模板名称查询process\_code。 | 新版 | 支持 | 支持 | 不支持 |
| [删除模板](/document/orgapp/delete-a-template-new) | 删除为企业创建的审批模板，同时删除该模板下创建的实例和待办任务。 | 新版 | 支持 | 支持 | 不支持 |
| [创建实例](/document/orgapp/create-a-ticket-approval-instance) | 创建不带流程的审批实例。 | 新版 | 支持 | 支持 | 不支持 |
| [更新实例状态](/document/orgapp/update-instance-status) | 更新实例状态。 | 新版 | 支持 | 支持 | 不支持 |
| [批量更新实例状态](/document/orgapp/update-the-status-of-multiple-instances-at-a-time-new) | 批量更新实例状态。 | 新版 | 支持 | 支持 | 不支持 |
| [创建流程中心待处理任务](/document/orgapp/create-pending-tasks-in-process-center) | 创建OA审批的待办任务。 | 新版 | 支持 | 支持 | 不支持 |
| [查询通过流程中心集成的OA审批任务](/document/orgapp/query-oa-approval-tasks-integrated-through-process-center) | 可以查询到用户运行中的审批任务。 | 新版 | 支持 | 支持 | 不支持 |
| [更新流程中心任务状态](/document/orgapp/update-process-center-task-status) | 更新待办任务的状态。 | 新版 | 支持 | 支持 | 不支持 |
| [批量取消OA审批待处理任务](/document/orgapp/cancel-multiple-oa-approval-tasks) | 批量取消流程中心待处理任务。 | 新版 | 支持 | 支持 | 不支持 |

## 智能填表

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取用户创建的填表模板列表](/document/orgapp/new-obtains-the-template-that-a-user-creates) | 调用本接口获取用户创建的填表模板列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取填表实例列表](/document/orgapp/obtain-the-table-filling-instance-list-data) | 调用本接口根据填表的Code获取填表实例列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取单条填表实例详情](/document/orgapp/obtains-the-instance-details-of-a-single-fill-table) | 调用本接口获取单条填表实例详情。 | 新版 | 支持 | 不支持 | 不支持 |

## 日程

### **用户访问控制**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建访问控制](/document/orgapp/create-schedule-access-control) | 调用本接口给指定日历添加访问控制。 | 新版 | 支持 | 不支持 | 支持 |
| [删除访问控制](/document/orgapp/delete-an-access-control-list) | 调用本接口删除访问控制。 | 新版 | 支持 | 不支持 | 支持 |
| [获取访问控制列表](/document/orgapp/obtain-the-access-control-list-of-the-calendar) | 调用本接口获取日历访问控制列表。 | 新版 | 支持 | 不支持 | 支持 |

### **日程**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建日程](/document/orgapp/create-event) | 调用本接口创建一个日程。 | 新版 | 支持 | 支持 | 支持 |
| [删除日程](/document/orgapp/delete-event) | 调用本接口删除指定日程。 | 新版 | 支持 | 支持 | 支持 |
| [修改日程](/document/orgapp/modify-event) | 调用本接口修改单个日程信息。 | 新版 | 支持 | 支持 | 支持 |
| [查询单个日程详情](/document/orgapp/query-details-about-an-event) | 调用本接口根据日程id查询单个日程详情。 | 新版 | 支持 | 支持 | 支持 |
| [查询日程列表](/document/orgapp/query-an-event-list) | 调用本接口查询一个用户给定时间范围内的日程，支持翻页和增量查询。 | 新版 | 支持 | 支持 | 支持 |
| [查询日程视图](/document/orgapp/query-schedule-view) | 调用本接口查询用户的钉钉主日历在某时间范围内的日程视图（循环日程展开）。 | 新版 | 支持 | 支持 | 支持 |

### **日程参与者**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [添加日程参与者](/document/orgapp/add-schedule-participant) | 添加日程参与者。 | 新版 | 支持 | 支持 | 支持 |
| [删除日程参与者](/document/orgapp/delete-schedule-participant) | 从日程参与者中删除指定的用户。 | 新版 | 支持 | 支持 | 支持 |
| [获取日程参与者](/document/orgapp/get-the-participants-of-a-schedule) | 获取日程参与者列表。 | 新版 | 支持 | 支持 | 支持 |
| [设置日程响应邀请状态](/document/orgapp/configure-response-status) | 设置日程响应邀请状态。 | 新版 | 支持 | 支持 | 支持 |

### **忙闲**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取用户忙闲信息](/document/orgapp/free-schedule) | 调用本接口查询指定用户列表在指定时间内的忙闲信息。 | 新版 | 支持 | 支持 | 支持 |

### **日历**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询日历](/document/orgapp/query-a-calendar) | 调用本接口查询用户日历。 | 新版 | 支持 | 支持 | 支持 |
| [订阅公共日历](/document/orgapp/subscribe-to-a-public-calendar) | 调用本接口订阅公共日历。 | 新版 | 支持 | 支持 | 支持 |
| [创建订阅日历](/document/orgapp/create-subscription-calendar) | 调用本接口创建订阅日历。 | 新版 | 支持 | 支持 | 支持 |
| [查询单个订阅日历详情](/document/orgapp/query-a-single-subscription-calendar) | 调用本接口查询订阅日历的详情信息。 | 新版 | 支持 | 支持 | 支持 |
| [更新订阅日历](/document/orgapp/update-subscription-calendar) | 调用本接口更新单个订阅日历信息。 | 新版 | 支持 | 支持 | 支持 |
| [删除订阅日历](/document/orgapp/delete-subscription-calendar) | 调用本接口删除订阅日历。 | 新版 | 支持 | 支持 | 支持 |

### **签到**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [针对单个日程进行签到](/document/orgapp/sign-in-for-a-single-schedule-new) | 根据日程ID对指定日程进行签到。 | 新版 | 支持 | 支持 | 支持 |
| [针对单个日程进行签退](/document/orgapp/sign-off-for-a-single-schedule) | 根据日程ID对指定日程进行签退。 | 新版 | 支持 | 支持 | 支持 |
| [查看单个日程的签到详情](/document/orgapp/view-the-check-in-details-of-a-single-schedule) | 根据日程ID查询单个日程签到与未签到人员列表。 | 新版 | 支持 | 支持 | 支持 |
| [查看单个日程的签退详情](/document/orgapp/view-the-billing-details-of-a-single-schedule) | 根据日程ID查询单个日程签退与未签退人员列表。 | 新版 | 支持 | 支持 | 支持 |

### **会议室**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取会议室忙闲信息](/document/orgapp/queries-free-and-busy-meeting-room-information) | 调用本接口获取会议室忙闲信息。 | 新版 | 支持 | 支持 | 不支持 |
| [预定会议室](/document/orgapp/add-a-meeting-room) | 调用本接口预定会议室。 | 新版 | 支持 | 支持 | 不支持 |
| [取消预定会议室](/document/orgapp/remove-a-meeting-room) | 调用本接口取消预定会议室 | 新版 | 支持 | 支持 | 不支持 |

## 待办任务

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建钉钉待办任务](/document/orgapp/add-dingtalk-to-do-task) | 发起一个钉钉待办任务。 | 新版 | 支持 | 支持 | 不支持 |
| [删除钉钉待办任务](/document/orgapp/delete-dingtalk-to-do-tasks) | 删除钉钉待办任务信息。 | 新版 | 支持 | 支持 | 不支持 |
| [更新钉钉待办任务](/document/orgapp/updates-dingtalk-to-do-tasks) | 更新钉钉待办任务信息及状态。 | 新版 | 支持 | 支持 | 不支持 |
| [更新钉钉待办执行者状态](/document/orgapp/update-dingtalk-to-do-status) | 当待办存在多个执行者时，可调用本接口更新部分执行者的完成状态。 | 新版 | 支持 | 支持 | 不支持 |
| [查询企业下用户待办列表](/document/orgapp/query-the-to-do-list-of-enterprise-users) | 获取该授权企业下某用户的待办列表。 | 新版 | 支持 | 支持 | 不支持 |

## Teambition 项目管理

### **项目**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [搜索企业项目模板](/document/orgapp/search-for-enterprise-custom-templates-by-project-template-name) | 按模板名字搜索项目模板信息。 | 新版 | 支持 | 支持 | 不支持 |
| [根据项目模板创建项目](/document/orgapp/create-a-project-from-a-project-template) | 根据项目模板创建项目。 | 新版 | 支持 | 支持 | 不支持 |
| [查询员工可见的项目分组](/document/orgapp/query-available-project-groups) | 查询员工可见的项目分组列表。 | 新版 | 支持 | 支持 | 不支持 |
| [更新项目所在的分组](/document/orgapp/update-project-grouping) | 更新项目所在分组。 | 新版 | 支持 | 支持 | 不支持 |
| [添加项目成员](/document/orgapp/add-project-members) | 批量添加项目成员。 | 新版 | 支持 | 支持 | 不支持 |
| [查询项目中文件操作日志](/document/orgapp/query-file-operation-logs-of-a-project) | 获取钉钉项目空间任务中文件的操作日志列表。 | 旧版 | 支持 | 不支持 | 不支持 |

### **任务**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建自由任务](/document/orgapp/create-a-free-task) | 创建一个钉钉自由任务。 | 新版 | 支持 | 支持 | 不支持 |
| [获取自由任务详情](/document/orgapp/queries-free-task-details) | 通过任务ID获取自由任务的详情 | 新版 | 支持 | 支持 | 不支持 |
| [批量获取自由任务详情](/document/orgapp/obtains-details-about-multiple-free-tasks) | 根据一组自由任务id，批量获取自由任务详情信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询优先级列表](/document/orgapp/query-a-priority-list) | 查询企业下设置的任务优先级列表。 | 新版 | 支持 | 支持 | 不支持 |
| [更新自由任务的优先级](/document/orgapp/change-free-task-priority) | 更新自由任务的优先级。 | 新版 | 支持 | 支持 | 不支持 |
| [更新自由任务标题](/document/orgapp/change-free-task-title) | 更新自由任务的标题。 | 新版 | 支持 | 支持 | 不支持 |
| [更新自由任务截止时间](/document/orgapp/change-free-task-deadline) | 更新自由任务的截止时间。 | 新版 | 支持 | 支持 | 不支持 |
| [更新自由任务执行者](/document/orgapp/change-free-task-executor) | 更新自由任务的执行者。 | 新版 | 支持 | 支持 | 不支持 |
| [增加或删除自由任务的参与者](/document/orgapp/change-task-participant) | 增加或删除自由任务的参与者。 | 新版 | 支持 | 支持 | 不支持 |
| [更新自由任务备注](/document/orgapp/update-free-task-notes) | 更新自由任务的备注信息。 | 新版 | 支持 | 支持 | 不支持 |
| [更新自由任务状态](/document/orgapp/change-free-task-status) | 更新自由任务的状态。 | 新版 | 支持 | 支持 | 不支持 |
| [创建项目任务](/document/orgapp/create-a-project-task) | 创建关联项目的任务 | 新版 | 支持 | 支持 | 不支持 |
| [添加任务的关联内容](/document/orgapp/create-a-linked-object-associated-with-a-task) | 添加任务的关联内容 | 新版 | 支持 | 支持 | 不支持 |
| [更新项目任务的自定义字段值](/document/orgapp/update-task-custom-field-value) | 更新项目任务的自定义字段值。 | 新版 | 支持 | 支持 | 不支持 |
| [查询项目中的任务](/document/orgapp/query-tasks-in-a-project) | 可根据指定条件查询项目中的任务。 | 新版 | 支持 | 支持 | 不支持 |

### **工时**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建计划工时](/document/orgapp/create-planned-work) | 新增项目任务中对应的计划工时。 | 新版 | 支持 | 支持 | 不支持 |
| [创建实际工时](/document/orgapp/create-actual-work) | 添加任务的实际工时。 | 新版 | 支持 | 支持 | 不支持 |

### **企业和用户**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取Teambition项目企业ID](/document/orgapp/obtain-the-teambition-enterprise-id) | 根据钉钉用户userId获取该用户所属钉钉企业绑定的Teambition项目企业ID。 | 新版 | 支持 | 支持 | 不支持 |
| [根据userId获取Teambition项目用户ID](/document/orgapp/obtain-dingtalk-teambition-user-id-based-on-userid) | 根据userId获取Teambition项目用户ID。 | 新版 | 支持 | 支持 | 不支持 |

## 日志

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建日志](/document/orgapp/create-a-log) | 调用本接口创建日志。 | 旧版 | 支持 | 支持 | 不支持 |
| [保存日志内容](/document/orgapp/save-custom-log-content) | 调用本接口保存自定义的日志内容。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取模板详情](/document/orgapp/query-template-details) | 调用本接口根据模板名称获取模板详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取用户发出的日志列表](/document/orgapp/query-logs-sent-by-an-employee) | 调用本接口获取用户发出的日志列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取用户发送日志的概要信息](/document/orgapp/view-log-summary-data) | 调用本接口根据员工userid或者日志模板名称，分页获取员工在一段时间范围内发送的日志概要信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取日志统计数据](/document/orgapp/query-log-statistics) | 调用该接口获取日志的已读人数、评论条数、评论人数、点赞人数。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取日志相关人员列表](/document/orgapp/obtains-a-list-of-log-related-personnel-by-type) | 调用该接口查询日志已读人员列表、评论人员列表或点赞人员列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取日志接收人员列表](/document/orgapp/queries-log-sharing-personnel) | 调用本接口获取日志接收人员列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取日志评论详情](/document/orgapp/queries-log-comment-details) | 调用该接口获取评论详情，包括评论人userid、评论内和评论时间。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取用户日志未读数](/document/orgapp/querying-the-employee-s-log-is-not-reading) | 调用本接口获取用户日志未读数。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取用户可见的日志模板](/document/orgapp/obtains-the-list-of-visible-log-templates-based-on-the) | 调用本接口根据userid获取用户可见的日志模板。 | 旧版 | 支持 | 不支持 | 不支持 |

## 签到

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取用户签到记录](/document/orgapp/obtain-the-check-in-records-of-multiple-users) | 调用本接口获取用户签到记录。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取部门用户签到记录](/document/orgapp/get-check-in-data) | 调用本接口获取部门用户签到记录。 | 旧版 | 支持 | 不支持 | 不支持 |

## **文档**

### **知识库**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [新建知识库](/document/orgapp/create-a-team-space) | 创建组织下的知识库。 | 新版 | 支持 | 支持 | 不支持 |
| [添加知识库成员](/document/orgapp/add-permissions-for-team-space-members) | 添加用户对知识库的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [查询知识库信息](/document/orgapp/query-team-space) | 查询知识库信息。 | 新版 | 支持 | 支持 | 不支持 |
| [更新知识库成员权限](/document/orgapp/update-team-space-user-permissions) | 更新用户对知识库的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [删除知识库成员](/document/orgapp/delete-team-space-user-permissions) | 删除用户对知识库的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [创建知识库文档](/document/orgapp/create-team-space-document) | 在知识库内创建文档或者文件夹。 | 新版 | 支持 | 支持 | 不支持 |
| [添加知识库文档成员](/document/orgapp/add-workspace-document-user-permissions) | 添加用户对知识库文档的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [修改知识库文档成员权限](/document/orgapp/update-team-space-document-user-permissions) | 更新用户对知识库内文档的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [删除知识库文档成员](/document/orgapp/delete-team-space-document-permissions) | 删除用户对知识库文档的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [查询用户有权限的知识库列表](/document/orgapp/querying-the-list-of-user-team-spaces) | 查询某个用户有权限的知识库列表。 | 新版 | 支持 | 支持 | 不支持 |
| [查询文档模板](/document/orgapp/query-a-document-template) | 查询知识库内的文档模板。 | 新版 | 支持 | 支持 | 不支持 |
| [查询知识库下的目录结构](/document/orgapp/query-the-directory-tree-in-the-knowledge-base) | 查询指定知识库下的目录结构。 | 新版 | 支持 | 支持 | 不支持 |
| [查询知识库节点信息](/document/orgapp/query-knowledge-base-node-information) | 查询知识库内的节点信息。 | 新版 | 支持 | 支持 | 不支持 |

### **表格**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建工作表](/document/orgapp/create-a-worksheet) | 在表格文档中创建一个新的工作表。 | 新版 | 支持 | 支持 | 不支持 |
| [删除工作表](/document/orgapp/delete-classic-workbooks) | 删除表格内的某个工作表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取工作表](/document/orgapp/obtain-worksheet-properties) | 获取某个工作表的基础属性。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取所有工作表](/document/orgapp/obtain-all-worksheets) | 获取指定表格中所有的工作表信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [指定行上方插入若干行](/document/orgapp/insert-rows-before-rows) | 在表格内指定行上方插入若干行。 | 新版 | 支持 | 支持 | 不支持 |
| [指定列左侧插入若干列](/document/orgapp/insert-column-before-column) | 在表格内指定列左侧插入若干列。 | 新版 | 支持 | 支持 | 不支持 |
| [删除行](/document/orgapp/delete-row) | 删除指定的行。 | 新版 | 支持 | 支持 | 不支持 |
| [删除列](/document/orgapp/delete-column) | 删除指定的列。 | 新版 | 支持 | 支持 | 不支持 |
| [设置行隐藏或显示](/document/orgapp/set-row-visibility) | 设置指定的行隐藏或者显示。 | 新版 | 支持 | 支持 | 不支持 |
| [设置列隐藏或显示](/document/orgapp/set-column-visibility) | 设置指定的列隐藏或者显示。 | 新版 | 支持 | 支持 | 不支持 |
| [更新单元格区域](/document/orgapp/update-cell-properties) | 更新单元格信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取单元格区域](/document/orgapp/get-cell-properties) | 获取单元格属性。 | 新版 | 支持 | 不支持 | 不支持 |
| [清除单元格区域内数据](/document/orgapp/clear-cell-data) | 清除指定区域内的数据，不包括格式。 | 新版 | 支持 | 支持 | 不支持 |
| [清除单元格区域内所有内容](/document/orgapp/clear-all) | 清除指定区域内的所有内容，包括格式。 | 新版 | 支持 | 支持 | 不支持 |

## **存储**

### **企业管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取企业信息](/document/orgapp/obtain-enterprise-storage-related-information) | 调用本接口，获取企业存储的相关信息。 | 新版 | 支持 | 支持 | 不支持 |

### **应用**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取群存储空间信息](/document/orgapp/obtain-group-storage-space-information) | 调用本接口，获取群存储空间信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [以应用身份发送文件给指定用户](/document/orgapp/sends-a-storage-file-to-a-specified-user) | 调用本接口，以应用身份发送文件给指定用户。 | 新版 | 支持 | 支持 | 不支持 |
| [发送文件到指定会话](/document/orgapp/send-file-to-specified-session) | 调用本接口，发送文件到指定会话。 | 新版 | 支持 | 不支持 | 不支持 |
| [发送文件链接到指定会话](/document/orgapp/send-a-file-link-to-the-specified-session) | 调用本接口，发送文件链接到指定会话。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取应用信息](/document/orgapp/obtains-the-information-about-the-current-application) | 调用本接口，获取应用信息。 | 新版 | 支持 | 支持 | 不支持 |

### **空间管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [添加空间](/document/orgapp/add-space) | 调用本接口，在企业存储内添加新空间。 | 新版 | 支持 | 支持 | 不支持 |
| [获取空间信息](/document/orgapp/get-space-information) | 调用本接口，获取存储空间的信息。 | 新版 | 支持 | 支持 | 不支持 |

### **文件管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [添加文件夹](/document/orgapp/add-folder) | 调用本接口，在存储空间内添加文件夹。 | 新版 | 支持 | 支持 | 不支持 |
| [复制文件或文件夹](/document/orgapp/copy-an-object) | 调用本接口，复制文件或文件夹。 | 新版 | 支持 | 支持 | 不支持 |
| [批量复制文件或文件夹](/document/orgapp/copy-files-or-folders-in-bulk) | 调用本接口，复制文件或文件夹。 | 新版 | 支持 | 支持 | 不支持 |
| [移动文件或文件夹](/document/orgapp/move-a-file-or-folder) | 调用本接口，移动文件或文件夹的位置。 | 新版 | 支持 | 支持 | 不支持 |
| [批量移动文件或文件夹](/document/orgapp/bulk-move-files-or-folders) | 调用本接口，批量移动文件或文件夹。 | 新版 | 支持 | 支持 | 不支持 |
| [重命名文件或文件夹](/document/orgapp/rename-a-file-or-folder) | 调用本接口，重命名文件或文件夹。 | 新版 | 支持 | 支持 | 不支持 |
| [删除文件或文件夹](/document/orgapp/delete-a-file-or-folder) | 调用本接口，删除文件或文件夹。 | 新版 | 支持 | 支持 | 不支持 |
| [批量删除文件或文件夹](/document/orgapp/delete-files-or-folders-in-bulk) | 调用本接口，批量删除文件或文件夹。 | 新版 | 支持 | 支持 | 不支持 |
| [恢复文件历史版本](/document/orgapp/restore-previous-versions-of-files) | 调用本接口，恢复文件历史版本。 | 新版 | 支持 | 支持 | 不支持 |
| [获取文件版本列表](/document/orgapp/obtains-a-list-of-file-versions) | 调用本接口，获取文件版本列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取文件或文件夹信息](/document/orgapp/obtain-file-or-folder-information) | 调用本接口，获取文件或文件夹信息。 | 新版 | 支持 | 支持 | 不支持 |
| [批量获取文件或文件夹信息](/document/orgapp/get-file-or-folder-information-in-bulk) | 批量获取文件或文件夹信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取文件或文件夹列表](/document/orgapp/obtain-the-file-list-storage) | 调用本接口，获取空间内的文件或文件夹列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取空间下所有文件或文件夹列表](/document/orgapp/get-a-list-of-all-files-or-folders-under-a) | 平铺获取空间下所有文件或文件夹列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取文件预览或编辑信息](/document/orgapp/obtains-the-object-preview-or-editing-information) | 调用本接口，更新文件或文件夹的应用属性。 | 新版 | 支持 | 支持 | 不支持 |
| [更新文件或文件夹的应用属性](/document/orgapp/update-file-application-properties) | 调用本接口，删除文件或文件夹的应用属性。 | 新版 | 支持 | 支持 | 不支持 |
| [删除文件或文件夹的应用属性](/document/orgapp/delete-file-app-attribute) | 调用本接口，获取文件预览或编辑的链接。 | 新版 | 支持 | 支持 | 不支持 |
| [三方个人应用批量获取文件缩略图](/document/orgapp/get-file-thumbnails-in-bulk) | 批量获取文件的缩略图信息。 | 新版 | 支持 | 支持 | 不支持 |

### **文件传输**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取文件上传信息](/document/orgapp/obtain-storage-upload-information) | 调用本接口，获取文件上传信息。 | 新版 | 支持 | 支持 | 不支持 |
| [提交文件](/document/orgapp/submit-documents) | 调用本接口，提交文件完成文件上传。 | 新版 | 支持 | 支持 | 不支持 |
| [初始化文件分片上传](/document/orgapp/initialize-a-multipart-upload-object) | 初始化文件分片上传。 | 新版 | 支持 | 支持 | 不支持 |
| [获取文件分片上传信息](/document/orgapp/obtains-the-information-about-multipart-uploads-of-an-object) | 获取文件分片后每片文件的上传信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取文件下载信息](/document/orgapp/obtains-the-download-information-about-a-file) | 调用本接口，获取存储空间内文件的下载信息。 | 新版 | 支持 | 不支持 | 不支持 |

### **权限管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [添加权限](/document/orgapp/add-storage-permissions) | 调用本接口，添加存储空间的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [删除权限](/document/orgapp/delete-storage-permissions) | 调用本接口，删除存储空间的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [修改权限](/document/orgapp/modify-storage-permissions) | 调用本接口，修改存储空间的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [获取权限列表](/document/orgapp/obtain-a-permission-list-storage) | 调用本接口，获取存储空间的权限列表。 | 新版 | 支持 | 支持 | 不支持 |

### **回收站管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取回收站信息](/document/orgapp/obtain-information-about-the-recycle-bin) | 获取回收站信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取回收项列表](/document/orgapp/gets-the-list-of-recycle-items) | 获取回收站内的回收项信息列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取回收项信息](/document/orgapp/obtain-recycling-item-information) | 获取回收项信息。 | 新版 | 支持 | 支持 | 不支持 |
| [还原回收项](/document/orgapp/restore-recycle-items) | 还原回收项。 | 新版 | 支持 | 支持 | 不支持 |
| [批量还原回收项](/document/orgapp/batch-restore-recycled-items) | 批量还原回收项。 | 新版 | 支持 | 支持 | 不支持 |
| [删除回收项](/document/orgapp/delete-recycle-item) | 删除回收站内的某个回收项。 | 新版 | 支持 | 支持 | 不支持 |
| [批量删除回收项](/document/orgapp/batch-delete-recycle-items) | 批量删除回收站内的回收项。 | 新版 | 支持 | 支持 | 不支持 |
| [清空回收站](/document/orgapp/empty-the-recycle-bin) | 根据回收站Id清空回收站。 | 新版 | 支持 | 支持 | 不支持 |

### **任务**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取存储中异步任务信息](/document/orgapp/get-the-asynchronous-task-information-in-storage) | 调用本接口，获取存储中异步任务信息。 | 新版 | 支持 | 支持 | 不支持 |

### **事件订阅**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [订阅文件变更事件](/document/orgapp/subscribe-to-file-change-events) | 订阅存储空间内文件的变更事件。 | 新版 | 支持 | 支持 | 不支持 |
| [取消订阅文件变更事件](/document/orgapp/unsubscribe-from-file-change-events) | 取消订阅存储空间内文件的变更事件。 | 新版 | 支持 | 支持 | 不支持 |

## 钉盘

### **空间管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [新建空间](/document/orgapp/new-space) | 新建企业共享空间。 | 新版 | 支持 | 支持 | 不支持 |
| [删除空间](/document/orgapp/delete-a-space) | 删除企业共享空间。 | 新版 | 支持 | 支持 | 不支持 |
| [获取空间列表](/document/orgapp/queries-a-space-list) | 查询钉盘空间列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取空间信息](/document/orgapp/obtain-space-information) | 获取空间详情信息。 | 新版 | 支持 | 支持 | 不支持 |
| [保存文件到自定义或审批钉盘空间](/document/orgapp/add-file-to-user-s-dingtalk-disk) | 将文件保存到自定义钉盘空间或审批附件钉盘空间。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取企业下的自定义空间](/document/orgapp/obtain-user-space-under-the-enterprise) | 获取企业下的自定义空间。 | 旧版 | 支持 | 支持 | 不支持 |

### **文件管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询文件（夹）列表](/document/orgapp/obtain-the-file-list) | 查询文件（夹）列表。 | 新版 | 支持 | 支持 | 不支持 |
| [查询文件（夹）信息](/document/orgapp/obtain-file-information) | 查询文件（夹）信息。 | 新版 | 支持 | 支持 | 不支持 |
| [添加文件（夹）](/document/orgapp/add-file) | 添加文件（夹）。 | 新版 | 支持 | 支持 | 不支持 |
| [删除文件（夹）](/document/orgapp/delete-objects) | 删除文件（夹）。 | 新版 | 支持 | 支持 | 不支持 |
| [移动文件（夹）](/document/orgapp/move-a-file) | 移动文件（夹）。 | 新版 | 支持 | 支持 | 不支持 |
| [修改文件（夹）名](/document/orgapp/rename-a-file) | 修改文件（夹）名称。 | 新版 | 支持 | 支持 | 不支持 |
| [拷贝文件（夹）](/document/orgapp/copy-files-folders) | 拷贝文件（夹）。 | 新版 | 支持 | 不支持 | 不支持 |

### **文件传输**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取文件上传信息](/document/orgapp/obtain-upload-information) | 获取文件上传信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取文件下载信息](/document/orgapp/obtain-download-file-info) | 获取文件下载信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [单步文件上传](/document/orgapp/single-step-file-upload) | 上传文件到钉盘。 | 旧版 | 支持 | 支持 | 不支持 |
| [开启分块上传事务](/document/orgapp/enable-upload-transaction) | 上传文件到钉盘。 | 旧版 | 支持 | 支持 | 不支持 |
| [上传文件块](/document/orgapp/upload-file-blocks) | 上传文件到钉盘。 | 旧版 | 支持 | 支持 | 不支持 |
| [提交文件上传事务](/document/orgapp/submit-a-file-upload-transaction) | 上传文件到钉盘。 | 旧版 | 支持 | 支持 | 不支持 |
| [发送钉盘文件给指定用户](/document/orgapp/sends-a-file-to-a-specified-user) | 将文件发送给指定用户，用户将收到以应用名义发送的一条文件消息。 | 旧版 | 支持 | 支持 | 不支持 |

### **回收站**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
|  | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询回收站文件（夹）列表](/document/orgapp/obtain-the-recycle-bin-folder-list) | 查询回收站内文件（夹）列表。 | 新版 | 支持 | 支持 | 不支持 |
| [还原回收站文件（夹）](/document/orgapp/restore-recycle-bin-files-folder) | 还原回收站中的文件或文件夹。 | 新版 | 支持 | 支持 | 不支持 |
| [删除回收站文件（夹）](/document/orgapp/delete-recycle-bin-files-folders) | 删除回收站文件或文件夹。 | 新版 | 支持 | 支持 | 不支持 |
| [清空回收站](/document/orgapp/empty-recycle-bin-files-folders) | 清空回收站。 | 新版 | 支持 | 支持 | 不支持 |

### **权限管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取权限列表](/document/orgapp/obtain-a-permission-list) | 获取用户对钉盘空间和文件的权限列表。 | 新版 | 支持 | 支持 | 不支持 |
| [添加权限](/document/orgapp/add-permissions) | 添加用户对钉盘空间和文件的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [删除权限](/document/orgapp/delete-permissions) | 删除用户对钉盘空间和文件的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [修改权限](/document/orgapp/modify-permissions) | 修改用户对钉盘空间和文件的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [添加自定义空间权限](/document/orgapp/add-custom-workspace-permissions) | 调用本接口授权企业下指定人员访问其使用的自定义空间。 | 新版 | 支持 | 支持 | 不支持 |

## **媒体文件**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [上传媒体文件](/document/orgapp/upload-media-files) | 调用该接口上传图片、语音媒体资源文件以及普通文件。 | 旧版 | 支持 | 支持 | 不支持 |

## 公告

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取用户可查看的公告](/document/orgapp/list-the-user-s-announcement-list) | 调用本接口可获取指定人员的公告信息，在企业自定义工作首页进行公告轮播展示。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取公告分类列表](/document/orgapp/obtains-the-list-of-categories-not-deleted-for-enterprise-announcements) | 调用本接口获取未删除的公告分类列表，如果公告类别已被删除，则无法获取。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取公告ID列表](/document/orgapp/obtains-the-id-list-of-announcements-that-are-not-deleted) | 调用该接口获取企业某公告分类下所有未删除的公告的ID列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取公告详情](/document/orgapp/obtains-the-details-of-a-bulletin-that-is-not-deleted) | 调用该接口根据公告ID获取未删除的公告的详情。 | 旧版 | 支持 | 不支持 | 不支持 |
| [创建公告](/document/orgapp/create-an-enterprise-announcement) | 调用本接口创建企业公告。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新公告](/document/orgapp/modify-the-announcement-according-to-the-announcement-id) | 调用该接口更新公告。 | 旧版 | 支持 | 不支持 | 不支持 |
| [删除公告](/document/orgapp/delete-announcements-based-on-the-announcement-id) | 调用该接口根据公告ID删除公告。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取公告钉盘空间信息](/document/orgapp/obtain-bulletin-nail-disk-space-information) | 调用本接口，获取公告附件存储的钉盘空间信息。 | 新版 | 支持 | 不支持 | 不支持 |

## **钉工牌**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建钉工牌电子码](/document/orgapp/create-a-badge-user-instance) | 调用本接口为用户创建钉工牌电子码实例，主要用于访客、会展等临时证场景。 | 新版 | 支持 | 支持 | 不支持 |
| [更新钉工牌电子码](/document/orgapp/update-dingtalk-user-instance) | 调用本接口更新用户钉工牌码的相关信息。 | 新版 | 支持 | 支持 | 不支持 |
| [解码钉工牌电子码](/document/orgapp/stack-dingtalk-badge) | 用本接口解码钉工牌码，获取关联的企业、用户userid等信息。 | 新版 | 支持 | 支持 | 不支持 |
| [通知支付结果](/document/orgapp/sync-dingtalk-badge-code-payment-result) | 用户使用钉工牌码扫码支付完成后，可调用本接口同步支付结果，并通知用户完成消费，同时为用户记录账单。 | 新版 | 支持 | 支持 | 不支持 |
| [通知退款结果](/document/orgapp/notification-dingtalk-badge-code-refund-result) | 用户使用钉工牌码支付后，如果发生退款，退款完成后，调用本接口同步退款结果，生成对应账单。 | 新版 | 支持 | 支持 | 不支持 |
| [同步钉工牌码验证结果](/document/isvapp/notification-dingtalk-badge-verification-result) | 用户使用钉工牌码进行身份验证后，可调用本接口通知身份验证结果。 | 新版 | 支持 | 支持 | 不支持 |
| [配置企业钉工牌](/document/orgapp/save-dingtalk-enterprise-instance) | 调用本接口为企业企业开通钉工牌电子码。 | 新版 | 支持 | 支持 | 不支持 |
| [钉工牌通知消息](/document/orgapp/dingtalk-badge-notification-message) | 调用本接口发送钉工牌通知消息。 | 新版 | 支持 | 支持 | 不支持 |

## **会议**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建视频会议](/document/orgapp/create-a-video-conference) | 创建视频会议。 | 新版 | 支持 | 支持 | 不支持 |
| [关闭视频会议](/document/orgapp/close-audio-video-conference) | 关闭视频会议，仅限该会议的主持人有关闭视频会议的权限。 | 新版 | 支持 | 支持 | 不支持 |
| [查询视频会议信息](/document/orgapp/querying-video-conference-information) | 查询视频会议的基本属性信息。 | 新版 | 支持 | 支持 | 不支持 |
| [批量查询视频会议信息](/document/orgapp/batch-query-of-video-conference-information) | 查询会议信息以及参会人员。 | 新版 | 支持 | 支持 | 不支持 |
| [查询视频会议成员](/document/orgapp/querying-video-conference-members) | 查询视频会议参会人员的信息。 | 新版 | 支持 | 支持 | 不支持 |
| [开启视频会议云录制](/document/orgapp/video-conference-open-cloud-recording) | 开启视频会议云录制。 | 新版 | 支持 | 支持 | 不支持 |
| [停止视频会议云录制](/document/orgapp/video-conferencing-stops-cloud-recording) | 停止视频会议云录制。 | 新版 | 支持 | 支持 | 不支持 |
| [查询会议录制的详情信息](/document/orgapp/query-recording-information) | 查询会议录制的详情信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询会议录制中的视频信息](/document/orgapp/queries-the-playback-information-about-a-recorded-cloud-video) | 查询会议录制中的视频信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询会议录制中的文本信息](/document/orgapp/queries-the-text-information-about-cloud-recording) | 查询视频会议录制的语音转文字信息 | 新版 | 支持 | 支持 | 不支持 |

## **直播**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建直播](/document/orgapp/create-live-streaming) | 创建直播。 | 新版 | 支持 | 支持 | 不支持 |
| [查询直播信息](/document/orgapp/queries-the-live-streaming-information) | 根据直播ID查询直播信息。 | 新版 | 支持 | 支持 | 不支持 |
| [修改直播属性信息](/document/orgapp/modify-live-streaming) | 修改直播属性信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询直播的观看数据](/document/orgapp/queries-the-playback-data-of-a-live-stream) | 查询直播的观看数据。 | 新版 | 支持 | 支持 | 不支持 |
| [查询直播观看人员信息](/document/orgapp/queries-the-viewing-information-of-viewers) | 查询直播观看人员的具体观看信息。 | 新版 | 支持 | 支持 | 不支持 |
| [删除直播](/document/orgapp/delete-live-streaming) | 删除直播。 | 新版 | 支持 | 支持 | 不支持 |

## **智能会议室**

### **会议室**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建会议室](/document/orgapp/create-a-meeting-room) | 创建会议室。 | 新版 | 支持 | 支持 | 不支持 |
| [删除会议室](/document/orgapp/delete-a-meeting-room) | 删除会议室。 | 新版 | 支持 | 支持 | 不支持 |
| [更新会议室信息](/document/orgapp/update-meeting-room-information) | 更新会议室信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询会议室列表](/document/orgapp/check-the-meeting-room-list) | 查询会议室列表。 | 新版 | 支持 | 支持 | 不支持 |
| [查询会议室详情](/document/orgapp/check-meeting-room-details) | 查询会议室详情。 | 新版 | 支持 | 支持 | 不支持 |
| [查询视频会议设备信息](/document/orgapp/querying-video-conference-device-information) | 查询视频会议设备信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [查询视频会议设备属性信息](/document/orgapp/querying-video-conference-device-attribute-information) | 查询视频会议设备属性信息。 | 新版 | 支持 | 不支持 | 不支持 |

### **会议室分组**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建会议室分组](/document/orgapp/create-a-meeting-room-group) | 创建会议室分组。 | 新版 | 支持 | 支持 | 不支持 |
| [删除会议室分组](/document/orgapp/delete-a-conference-room-group) | 删除会议室分组。 | 新版 | 支持 | 支持 | 不支持 |
| [更新会议室分组信息](/document/orgapp/update-meeting-room-groups) | 更新会议室分组的信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询会议室分组列表](/document/orgapp/query-meeting-rooms-groups) | 查询会议室分组列表。 | 新版 | 支持 | 支持 | 不支持 |
| [查询会议室分组信息](/document/orgapp/query-meeting-room-groups) | 查询会议室分组信息。 | 新版 | 支持 | 支持 | 不支持 |

## **荣誉**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询当前企业下可颁发的荣誉列表](/document/orgapp/query-the-list-of-honors-that-can-be-issued-under) | 查询当前企业下可颁发的荣誉列表。 | 新版 | 支持 | 支持 | 不支持 |
| [给员工颁发荣誉](/document/orgapp/award-of-honor) | 用于给组织内的员工颁发荣誉。 | 新版 | 支持 | 支持 | 不支持 |
| [查询员工已获得的组织荣誉](/document/orgapp/check-the-honors-that-an-employee-has-received) | 查询某个员工获得的组织荣誉记录。 | 新版 | 支持 | 支持 | 不支持 |

## 钉钉运动

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询用户是否参与企业步数排行榜](/document/orgapp/check-whether-dingtalk-is-enabled) | 本接口用于查询用户是否参与企业的步数排行榜。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取个人或部门钉钉运动数据](/document/orgapp/queries-individual-or-department-dingtalk-exercise-steps) | 调用本接口查询企业用户或部门每天的钉钉运动步数。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量获取钉钉运动数据](/document/orgapp/queries-the-number-of-dingtalk-movement-steps-of-multiple-users) | 调用本接口批量获取钉钉运动数据。 | 旧版 | 支持 | 支持 | 不支持 |

## **智能交互**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [AI 助理发消息（回复消息模式）](/document/orgapp/ai-assistant-messages-reply-mode) | 用于开发者可以通过钉钉 AI 助理用自定义互动卡片智能消息回复用户。 | 新版 | 支持 | 不支持 | 不支持 |
| [AI 助理预备发消息（主动发送模式）](/document/orgapp/api-prepare) | 用于给用户发送一个状态为“准备中”的消息框，让用户有一个良好的交互体验，同时开发者能收到会话凭证，用于后续的消息更新和结束。 | 新版 | 支持 | 不支持 | 不支持 |
| [AI 助理更新消息（主动发送模式）](/document/orgapp/api-update) | 用于根据会话凭证，更新相应消息框，且支持多次更新。 | 新版 | 支持 | 不支持 | 不支持 |
| [AI 助理结束发消息（主动发送模式）](/document/orgapp/api-finish) | 用于结束消息框的更新，把会话凭证吊销。 | 新版 | 支持 | 不支持 | 不支持 |

## **组织大脑**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [数据集成人员信息同步](/document/orgapp/api-hrbrainimportempinfo) | 用于将人员信息同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成入职信息同步](/document/orgapp/api-hrbrainimportregist) | 用于将入职信息同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成离职信息同步](/document/orgapp/api-hrbrainimportdimission) | 用于将离职信息同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成工作经历同步](/document/orgapp/api-hrbrainimportworkexp) | 用于将工作经历同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成教育经历同步](/document/orgapp/api-hrbrainimporteduexp) | 用于将教育经历同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成绩效记录同步](/document/orgapp/api-hrbrainimportperfeval) | 用于将绩效记录同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成晋升记录同步](/document/orgapp/api-hrbrainimportpromeval) | 用于将晋升记录同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成奖励记录同步](/document/orgapp/api-hrbrainimportawarddetail) | 用于将奖励记录同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成处分记录同步](/document/orgapp/api-hrbrainimportpundetail) | 用于将处分记录同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成基础标签同步](/document/orgapp/api-hrbrainimportlabelbase) | 用于将基础标签同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成专业技能同步](/document/orgapp/api-hrbrainimportlabelprofskill) | 用于将专业技能同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成领域经验同步](/document/orgapp/api-hrbrainimportlabelindustry) | 用于将领域经验同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成盘点数据同步](/document/orgapp/api-hrbrainimportlabelinventory) | 用于将盘点数据同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成自定义标签同步](/document/orgapp/api-hrbrainimportlabelcustom) | 用于将自定义标签同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成组织架构同步](/document/orgapp/api-hrbrainimportdeptinfo) | 用于将组织架构同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |
| [数据集成异动记录同步](/document/orgapp/api-hrbrainimporttransfereval) | 用于将人员异动记录同步至组织大脑，支持批量同步。 | 新版 | 支持 | 不支持 | 不支持 |

## **企业百科**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [新增词条](/document/orgapp/new-entry) | 新增企业词条。 | 新版 | 支持 | 支持 | 不支持 |
| [审核词条](/document/orgapp/review-entries) | 审核新增的企业词条。 | 新版 | 支持 | 支持 | 不支持 |
| [根据词条ID查询详情](/document/orgapp/query-entry) | 根据词条标识ID，查询词条详情。 | 新版 | 支持 | 支持 | 不支持 |
| [更新词条](/document/orgapp/update-entry) | 更新词条信息。 | 新版 | 支持 | 支持 | 不支持 |
| [删除词条](/document/orgapp/delete-entry) | 删除企业词条。 | 新版 | 支持 | 支持 | 不支持 |
| [分页获取企业词条信息](/document/orgapp/entry-search) | 分页获取企业词条信息 | 新版 | 支持 | 支持 | 不支持 |
| [匹配文本中的词条](/document/orgapp/enterprise-encyclopedia-match-entries-in-a-text) | 将文本与企业词条进行匹配，获取与词条全称或别名相同的文本内容。 | 新版 | 支持 | 支持 | 不支持 |
| [查询词条详情](/document/orgapp/enterprise-encyclopedia-query-entry-details-by-entry-name) | 根据词条名称查询该词条相关详情信息。 | 新版 | 支持 | 支持 | 不支持 |

## 宜搭

### 流程

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [发起宜搭审批流程](/document/orgapp/initiate-the-approval-process) | 发起宜搭审批流程到钉钉开放平台。 | 新版 | 支持 | 支持 | 不支持 |
| [删除流程实例](/document/orgapp/delete-process-instance) | 删除流程实例。 | 新版 | 支持 | 支持 | 不支持 |
| [终止流程实例](/document/orgapp/terminate-a-process-instance) | 终止流程实例。 | 新版 | 支持 | 支持 | 不支持 |
| [获取实例ID列表](/document/orgapp/obtains-a-list-of-instance-ids) | 获取实例ID列表。 | 新版 | 支持 | 支持 | 不支持 |
| [批量获取流程实例列表](/document/orgapp/queries-multiple-process-instances) | 根据流程实例ID，批量获取对应的流程实例详情。 | 新版 | 支持 | 支持 | 不支持 |
| [获取流程实例](/document/orgapp/obtain-process-instance) | 获取宜搭的流程实例信息。 | 新版 | 支持 | 支持 | 不支持 |
| [根据流程实例ID获取流程实例](/document/orgapp/queries-a-process-instance-based-on-its-id) | 根据指定流程实例ID获取流程实例详情。 | 新版 | 支持 | 支持 | 不支持 |

### 表单

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取指定应用下的表单列表](/document/orgapp/depending-on-the-application-id-to-get-the-form-list) | 分页获取应用下的表单列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取表单内的组件信息](/document/orgapp/get-form-field-information-based-on-form-uuid) | 根据表单ID，获取单据或流程表单内的组件信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询表单实例数据](/document/orgapp/querying-form-instance-data) | 查询表单实例数据。 | 新版 | 支持 | 支持 | 不支持 |
| [保存表单数据](/document/orgapp/save-form-data) | 新增一条无审批流程的宜搭表单实例。 | 新版 | 支持 | 支持 | 不支持 |
| [更新表单数据](/document/orgapp/update-form-data) | 更新表单数据。 | 新版 | 支持 | 支持 | 不支持 |
| [查询表单数据](/document/orgapp/query-form-data) | 通过表单实例ID查询表单数据。 | 新版 | 支持 | 支持 | 不支持 |
| [获取员工组件的值](/document/orgapp/gets-the-value-of-the-employee-component) | 获取员工组件的值。 | 新版 | 支持 | 支持 | 不支持 |
| [获取表单组件定义列表](/document/orgapp/get-a-list-of-form-component-definitions) | 获取表单组件定义列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取子表组件数据](/document/orgapp/obtain-child-table-component-data) | 通过表单实例ID和子表组IDd获取子表组件数据。 | 新版 | 支持 | 支持 | 不支持 |
| [删除表单数据](/document/orgapp/delete-form-data) | 删除表单数据。 | 新版 | 支持 | 支持 | 不支持 |
| [获取多个表单实例ID](/document/orgapp/obtain-the-ids-of-multiple-form-instances) | 获取多个表单实例ID。 | 新版 | 支持 | 支持 | 不支持 |
| [批量获取表单实例数据](/document/orgapp/obtain-multiple-form-instance-data) | 批量获取表单实例详情信息。 | 新版 | 支持 | 支持 | 不支持 |
| [批量删除表单实例](/document/orgapp/delete-multiple-form-instances) | 批量删除表单实例数据。 | 新版 | 支持 | 支持 | 不支持 |
| [批量创建表单实例](/document/orgapp/create-multiple-form-instances) | 批量创建表单实例数据。 | 新版 | 支持 | 支持 | 不支持 |
| [批量更新表单实例内的组件值](/document/orgapp/batch-update-of-component-values-in-form-instances) | 根据宜搭表单实例Id，批量更新宜搭表单实例的组件值。 | 新版 | 支持 | 支持 | 不支持 |
| [新增或更新表单实例](/document/orgapp/add-or-update-form-instances) | 使用筛选条件新增或更新表单实例。 | 新版 | 支持 | 支持 | 不支持 |
| [通过高级查询条件获取表单实例数据（包括子表单组件数据）](/document/orgapp/query-form-instances-using-advanced-search-conditions) | 使用筛选条件获取表单实例详情。 | 新版 | 支持 | 支持 | 不支持 |
| [通过高级查询条件获取表单实例数据（不包括子表单组件数据）](/document/orgapp/obtain-form-instance-data-using-advanced-query-conditions-excluding-subform) | 使用筛选条件获取表单实例详情，不包括子表单组件数据。 | 新版 | 支持 | 支持 | 不支持 |
| [通过表单实例数据批量更新表单实例](/document/orgapp/update-multiple-form-instances-with-the-form-instance-data) | 根据宜搭表单组件数据，批量更新表单实例信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询表单的变更记录](/document/orgapp/change-records-of-query-forms) | 查询表单的变更记录 | 新版 | 支持 | 支持 | 不支持 |

### 任务

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取审批记录](/document/orgapp/queries-an-approval-record) | 获取审批记录。 | 新版 | 支持 | 支持 | 不支持 |
| [同意或拒绝宜搭审批任务](/document/orgapp/execute-approval-tasks) | 同意或拒绝宜搭审批任务。 | 新版 | 支持 | 支持 | 不支持 |
| [获取组织内某人提交的任务](/document/orgapp/obtains-the-tasks-submitted-by-someone-in-an-organization) | 获取组织内某人提交的任务。 | 新版 | 支持 | 支持 | 不支持 |
| [获取组织内已完成的审批任务](/document/orgapp/obtains-the-completed-approval-tasks-in-an-organization) | 获取组织内已完成的审批任务。 | 新版 | 支持 | 支持 | 不支持 |
| [转交任务](/document/orgapp/transfer-tasks) | 转交任务。 | 新版 | 支持 | 支持 | 不支持 |
| [查询流程运行任务（VPC）](/document/orgapp/query-process-running-tasks-vpc) | 查询流程运行任务（VPC）。 | 新版 | 支持 | 支持 | 不支持 |
| [获取任务列表（组织维度）](/document/orgapp/query-tasks-from-the-organization-dimension) | 获取组织维度任务列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取发送给用户的通知](/document/orgapp/get-notifications-sent-to-users) | 获取发送给用户的通知。 | 新版 | 支持 | 支持 | 不支持 |
| [查询抄送我的任务列表（应用维度）](/document/orgapp/query-copied-my-task-list-application-dimension) | 查询抄送我的任务列表（应用维度）。 | 新版 | 支持 | 支持 | 不支持 |
| [批量执行宜搭审批任务](/document/orgapp/batch-execution-should-take-the-lead-of-approval-tasks) | 批量执行宜搭表单实例的审批任务。 | 新版 | 支持 | 支持 | 不支持 |
| [提交评论](/document/orgapp/submit-comment) | 提交表单或流程实例下的评论。 | 新版 | 支持 | 支持 | 不支持 |
| [批量查询宜搭表单实例的评论](/document/orgapp/batch-query-of-comments-appropriate-for-form-instances) | 批量查询宜搭表单下的所有评论。 | 新版 | 支持 | 支持 | 不支持 |

### **附件**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取宜搭附件临时免登地址](/document/orgapp/obtain-the-temporary-free-access-address-of-yixian-accessories) | 获取宜搭附件临时免登地址。 | 新版 | 支持 | 支持 | 不支持 |

### **应用**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询宜搭应用列表](/document/orgapp/query-the-application-list) | 查询组织下的宜搭应用列表。 | 新版 | 支持 | 支持 | 不支持 |

### **服务日志**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取集成自动化日志详情](/document/orgapp/api-getautoflowlogdetail) | 用于通过集成自动化的实例 id 获取日志详情信息。 | 新版 | 支持 | 支持 | 不支持 |
| [分页获取集成自动化日志列表](/document/orgapp/api-pageautoflowlog) | 用于根据表单信息数据，获取集成自动化日志列表。 | 新版 | 支持 | 支持 | 不支持 |

### 服务调用

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询宜搭表单服务调用执行记录](/document/orgapp/the-query-should-be-based-on-the-execution-records-of) | 根据宜搭表单Id查询对应的服务调用执行记录信息。 | 新版 | 支持 | 支持 | 不支持 |

## 专属钉钉

### **可信设备**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [新增可信设备信息](/document/orgapp/add-information-about-a-trusted-device) | 调用本接口新增一个可信设备。 | 新版 | 支持 | 不支持 | 不支持 |
| [批量新增可信设备](/document/orgapp/create-multiple-trusted-devices) | 用于给某个用户批量新增可信设备。 | 新版 | 支持 | 支持 | 不支持 |
| [查询可信设备详细信息](/document/orgapp/query-trusted-device-details) | 调用本接口查询组织内员工的可信设备详细信息。 | 新版 | 支持 | 不支持 | 不支持 |

### **审计**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取审计协议签署人员信息](/document/orgapp/obtains-the-information-about-the-persons-who-sign-the-audit-1) | 本接口用于获取审计应用内已签署和未签署人员的信息。 | 新版 | 支持 | 支持 | 不支持 |

### **产业互联**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取可打标部门列表](/document/orgapp/obtains-a-list-of-departments-that-can-be-marked) | 获取可打标部门的信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取子标签列表](/document/orgapp/obtain-child-tags-from-a-parent-tag) | 使用父标签ID获取子标签列表。 | 新版 | 支持 | 支持 | 不支持 |
| [设置部门伙伴类型和伙伴编码](/document/orgapp/set-department-partner-type-and-partner-code) | 通过部门ID设置部门伙伴类型和伙伴编码。 | 新版 | 支持 | 支持 | 不支持 |
| [修改伙伴类型可见性](/document/orgapp/modify-partner-type-visibility) | 修改伙伴标签类型可见性。 | 新版 | 支持 | 支持 | 不支持 |
| [查询伙伴角色列表](/document/orgapp/query-the-list-of-partners) | 根据父标签ID获取角色列表。 | 新版 | 支持 | 支持 | 不支持 |
| [修改角色可见性](/document/orgapp/modify-role-visibility) | 修改角色标签可见性。 | 新版 | 支持 | 支持 | 不支持 |
| [发送邀请函](/document/orgapp/send-invitations) | 向下游企业发送加入合作伙伴邀请函。 | 新版 | 支持 | 支持 | 不支持 |
| [根据userId查询人员的标签信息](/document/orgapp/you-can-call-this-operation-to-retrieve-the-user-tag) | 查询上下游组织内人员的标签信息。 | 新版 | 支持 | 支持 | 不支持 |

### **文件**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [发送文件更改的评论](/document/orgapp/send-comments-on-file-changes) | 发送文件更改的评论。 | 新版 | 支持 | 支持 | 不支持 |
| [获取文件操作记录](/document/orgapp/obtain-file-operation-records) | 获取专属钉钉内成员所有所在组织的操作文件或文档的记录。 | 新版 | 支持 | 不支持 | 不支持 |

### **DING**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [DING服务](/document/orgapp/send-in-application-ding) | 通过专属DING服务中设置的互动服务窗来发送应用内DING。 | 新版 | 支持 | 不支持 | 不支持 |
| [发送电话DING](/document/orgapp/outgoing-phone-ding) | 通过互动服务窗的服务号发送电话DING。 | 新版 | 支持 | 不支持 | 不支持 |

### **企业内部群**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [企业内部群禁言或解除禁言](/document/orgapp/exclusive-dingtalk-group-ban) | 设置企业内部群禁言或者解除企业内部群禁言。 | 新版 | 支持 | 支持 | 不支持 |
| [获取群活跃明细列表](/document/orgapp/obtains-the-group-activity-details-list) | 获取自己企业下群组的相关信息列表。 | 新版 | 支持 | 支持 | 不支持 |
| [查询企业内部群信息](/document/orgapp/obtain-group-info) | 调用本接口查询企业内部群信息。 | 旧版 | 支持 | 支持 | 不支持 |

### **数据统计**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取视频会议详情](/document/orgapp/get-video-meeting-details) | 调用本接口获取视频会议详情。 | 新版 | 支持 | 支持 | 不支持 |
| [获得组织维度日程相关信息](/document/orgapp/queries-the-number-of-people-who-have-created-an-event) | 调用本接口获得组织维度日程相关信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [获得企业创建日志相关信息（部门维度）](/document/orgapp/obtains-information-about-a-created-enterprise-log-from-the-department) | 调用本接口按部门维度获取企业创建日志相关信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [获得企业创建日志相关信息（组织维度）](/document/orgapp/obtains-information-about-a-created-enterprise-log-from-the-organization) | 调用本接口获取企业组织维度创建日志相关数据。 | 新版 | 支持 | 不支持 | 不支持 |
| [获得用户创建文档数和创建文档人数（部门维度）](/document/orgapp/queries-the-number-dingtalk-documents-created-per-day-in-a) | 调用本接口按部门维度获取企业创建钉钉文档数。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取用户创建文档数和创建文档人数（组织维度）](/document/orgapp/queries-the-number-dingtalk-documents-created-per-day-in-an) | 调用本接口按组织维度获取企业创建钉钉文档数。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取发布智能填表数量和使用智能填表人数（部门维度）](/document/orgapp/obtains-the-number-of-tables-published-by-the-enterprise-from) | 调用本接口按部门维度获取企业发布智能填表数。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业发布智能填表数（组织维度）](/document/orgapp/queries-the-number-of-tables-published-in-an-organization) | 调用本接口按组织维度获取企业发布智能填表数。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取互动服务窗相关数据](/document/orgapp/queries-the-data-about-the-interactive-service-window) | 调用本接口获取互动服务窗应用分析相关数据。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取用户月活跃数据](/document/orgapp/retrieves-the-user-s-monthly-active-data) | 调用本接口获取组织维度用户月活跃数据。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取未活跃用户登录明细](/document/orgapp/obtains-the-logon-details-of-inactive-users) | 调用本接口获取用户版本分布情况。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取用户版本分布情况](/document/orgapp/queries-the-distribution-of-user-versions) | 调用本接口未活跃用户登录明细统计信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取视频直播明细列表](/document/orgapp/queries-the-details-list-of-apsaravideo-live) | 调用本接口获取视频直播明细列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取视频直播观看人员列表](/document/orgapp/query-users-of-apsaravideo-live) | 调用本接口获取观看视频直播的人员列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业视频直播统计列表（部门维度）](/document/orgapp/live-broadcast-summary-statistics-of-key-account-departments) | 调用本接口按部门直播视频统计列表数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业视频直播统计数据](/document/orgapp/query-live-streaming-statistics) | 调用本接口获取企业视频直播统计数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业某天的视频会议统计数据](/document/orgapp/video-conferencing-statistics-query-v2-for-key-accounts) | 获取企业在某一天的视频会议统计数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业某天的所有部门视频会议统计数据](/document/orgapp/video-conferencing-statistics-list-for-key-accounts-and-departments) | 查询企业在某天各部门视频会议统计列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业视频会议明细列表](/document/orgapp/video-conference-details-for-key-accounts) | 获取企业视频会议明细列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业某天的所有部门电话会议统计列表](/document/orgapp/major-customer-department-dimension-teleconference-statistics) | 查询企业在某天各部门电话会议汇总统计列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业电话会议明细列表](/document/orgapp/major-account-conference-call-details-list) | 查询企业在某天发起的电话会议列表及详情。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业某天的电话会议数据](/document/orgapp/major-customer-teleconference-statistics-interface) | 获取企业某天的电话会议数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业各类群组创建情况](/document/orgapp/api-for-obtaining-the-creation-status-of-various-groups) | 查询企业各类群组创建情况。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业聊天数据](/document/orgapp/chat-data-statistics-query-for-key-accounts) | 查询当前企业每天的聊天汇总数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业部门聊天数据（部门维度）](/document/orgapp/dingtalk-chat-information-in-key-accounts) | 查询企业各部门聊天数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业应用访问情况](/document/orgapp/queries-the-daily-usage-summary-of-microapplications-in-an-enterprise) | 查询当前企业每天的微应用使用汇总数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [统计企业活跃用户](/document/orgapp/query-for-dau-statistics) | 查询企业的DAU（日活跃用户数量）汇总数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [企业活跃用户统计列表（部门维度）](/document/orgapp/query-the-statistics-of-active-users-in-a-department-of) | 查询部门维度的活跃用户统计数据列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [查询企业通讯录未激活用户列表](/document/orgapp/queries-the-list-of-inactive-accounts-in-the-key-account) | 查询当前企业当前通讯录未激活用户明细列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业DING使用数据](/document/orgapp/enterprise-ding-quantity-statistics) | 查询企业各类DING的使用情况。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取企业DING使用数据（部门维度）](/document/orgapp/query-the-departmental-transmission-status-of-key-clients) | 查询企业各部门各类DING的使用情况。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取防截屏操作记录](/document/orgapp/obtain-anti-screen-capture-operation-records) | 获取企业内员工防截屏操作记录。 | 新版 | 支持 | 不支持 | 不支持 |

### **互动服务窗**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [新增服务号](/document/orgapp/add-service-number) | 新增一个服务号。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新服务号](/document/orgapp/service-number-update) | 更新指定服务号的相关信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [查询服务号列表](/document/orgapp/query-the-list-of-service-ids) | 查询当前组织的服务号列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [查询服务号详情](/document/orgapp/query-the-details-of-a-service-number) | 根据服务号的unionid查询服务号详情。 | 旧版 | 支持 | 不支持 | 不支持 |
| [新增文章](/document/orgapp/new-article) | 新增一篇文章。 | 旧版 | 支持 | 不支持 | 不支持 |
| [删除文章](/document/orgapp/delete-article) | 删除一篇指定的文章。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新文章](/document/orgapp/save-article-details) | 更新指定文章。 | 旧版 | 支持 | 不支持 | 不支持 |
| [查询文章列表](/document/orgapp/query-articles) | 查询文章列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取文章详情](/document/orgapp/get-articles) | 查询一篇文章的详细信息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [发布文章](/document/orgapp/article-publishing-interface) | 发布文章。 | 旧版 | 支持 | 不支持 | 不支持 |
| [新增图文卡片](/document/orgapp/new-message-card) | 新增消息卡片。 | 旧版 | 支持 | 不支持 | 不支持 |
| [删除图文卡片](/document/orgapp/delete-message-cards) | 删除指定的消息卡片素材。 | 旧版 | 支持 | 不支持 | 不支持 |
| [删除图文卡片](/document/orgapp/delete-message-cards) | 获取消息卡片详情。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新图文卡片](/document/orgapp/message-card-material-update-operation) | 更新消息卡片。 | 旧版 | 支持 | 不支持 | 不支持 |
| [查询图文卡片列表](/document/orgapp/query-the-list-of-message-cards) | 查询消息卡片列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [消息撤回](/document/orgapp/service-id-message-recall) | 根据消息发送的任务id撤回消息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [消息群发](/document/orgapp/group-messaging-apis-for-interactive-service-windows) | 群发消息。 | 旧版 | 支持 | 不支持 | 不支持 |
| [服务号菜单更新](/document/orgapp/service-no-menu-update) | 更新服务号的会话菜单。 | 旧版 | 支持 | 不支持 | 不支持 |
| [查询服务号菜单](/document/orgapp/query-service-number-menu) | 查询指定服务号的会话菜单。 | 旧版 | 支持 | 不支持 | 不支持 |

### **获取年报数据**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取年报数据](/document/orgapp/obtain-annual-report-data) | 根据不同数据维度，获取企业年报数据。 | 旧版 | 支持 | 不支持 | 不支持 |

## 客户管理

### **客户**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建个人或企业客户数据](/document/orgapp/add-crm-personal-customers) | 添加CRM个人客户或企业客户。 | 新版 | 支持 | 支持 | 不支持 |
| [批量新增个人或企业客户数据](/document/orgapp/add-multiple-relationship-data-in-batches) | 批量新增个人客户、企业客户数据。 | 新版 | 支持 | 支持 | 不支持 |
| [更新个人或企业客户数据](/document/orgapp/update-crm-personal-customers) | 更新CRM个人客户或企业客户信息。 | 新版 | 支持 | 支持 | 不支持 |
| [批量更新个人或企业客户数据](/document/orgapp/update-multiple-relational-data-tables-at-a-time) | 批量修改个人客户、企业客户数据。 | 新版 | 支持 | 支持 | 不支持 |
| [删除个人或企业客户数据](/document/orgapp/delete-crm-personal-customer) | 删除CRM个人客户或企业客户数据。 | 新版 | 支持 | 支持 | 不支持 |
| [批量获取个人或企业客户数据](/document/orgapp/acquire-crm-individual-customers-in-batches) | 批量获取CRM个人客户或企业客户。 | 新版 | 支持 | 支持 | 不支持 |
| [获取个人或企业客户的元数据](/document/orgapp/get-metadata-description-of-crm-customer-object-1) | 获取CRM个人客户或企业客户的元数据描述。 | 新版 | 支持 | 支持 | 不支持 |
| [获取全量个人或企业客户数据](/document/orgapp/crm-obtains-all-private-sea-customer-data) | 获取CRM个人或企业客户数据。 | 新版 | 支持 | 支持 | 不支持 |
| [根据指定条件查询个人或企业客户数据](/document/orgapp/obtains-crm-individual-customers-in-batches-based-on-specified-query) | 根据指定条件查询CRM个人客户或企业客户数据。 | 新版 | 支持 | 支持 | 不支持 |
| [获取个人或企业客户查重字段](/document/orgapp/obtain-duplicate-check-fields) | 获取客户管理中设置个人客户、企业客户的查重字段。 | 新版 | 支持 | 支持 | 不支持 |
| [查询客户数据](/document/orgapp/querying-customer-data) | 根据客户的unionId查询客户详情信息。 | 新版 | 支持 | 支持 | 不支持 |
| [查询客户数据](/document/orgapp-server/querying-customer-data#doc-api-dingtalk-QueryRelationDatasByTargetId) | 调用本接口根据客户的unionId查询客户详情信息。 | 新版 | 支持 | 支持 | 不支持 |

### **联系人**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [批量新增联系人数据](/document/orgapp/add-contact-data-in-batches) | 调用本接口批量新增联系人数据。 | 新版 | 支持 | 支持 | 不支持 |
| [批量修改联系人数据](/document/orgapp/modify-contact-data-in-batches) | 调用本接口批量修改联系人数据。 | 新版 | 支持 | 支持 | 不支持 |
| [删除联系人数据](/document/orgapp/delete-crm-contact) | 调用本接口删除当前组织CRM指定联系人的数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [根据指定条件查询联系人数据](/document/orgapp/dingtalk-the-contact-data-query-api) | 调用本接口根据指定查询条件批量获取联系人数据。 | 旧版 | 支持 | 支持 | 不支持 |
| [按照ID列表批量获取联系人数据](/document/orgapp/retrieves-contact-data-in-batches-based-on-the-id-list) | 调用本接口根据联系人实例id列表批量获取联系人数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取联系人的元数据](/document/orgapp/gets-the-metadata-description-of-a-crm-contact-object) | 调用本接口获取钉钉CRM联系人的元数据描述。 | 旧版 | 支持 | 支持 | 不支持 |

### **跟进记录**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [根据指定条件查询跟进记录数据](/document/orgapp/query-and-dingtalk-data-of-track-records-in-apsara-stack) | 调用本接口根据指定查询条件批量获取跟进记录数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [根据ID列表批量获取跟进记录数据](/document/orgapp/dingtalk-the-primary-data-of-apsara-stack-agility-paas-allows-you) | 调用本接口根据实例ID列表批量获取跟进记录数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取跟进记录对象的元数据](/document/orgapp/obtains-the-metadata-description-of-the-crm-follow-up-record-object) | 调用本接口读取钉钉CRM跟进记录对象的元数据。 | 旧版 | 支持 | 支持 | 不支持 |
| [批量新增跟进记录数据](/document/orgapp/batch-add-follow-up-record-data) | 调用本接口批量新增跟进记录数据。 | 新版 | 支持 | 支持 | 不支持 |
| [批量更新跟进记录数据](/document/orgapp/batch-update-follow-up-record-data) | 调用本接口批量更新跟进记录数据。 | 新版 | 支持 | 支持 | 不支持 |
| [批量删除跟进记录数据](/document/orgapp/batch-delete-follow-up-record-data) | 调用本接口批量删除跟进记录数据。 | 新版 | 支持 | 支持 | 不支持 |

### **自定义对象**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [删除CRM自定义对象数据](/document/orgapp/delete-crm-custom-object-data) | 删除CRM自定义对象数据。 | 新版 | 支持 | 不支持 | 不支持 |
| [创建CRM自定义对象数据](/document/orgapp/dingtalk-paas-master-create-custom-crm-object-data) | 调用本接口创建自定义对象数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [更新自定义对象数据](/document/orgapp/crm-master-data-opens-interface-for-updating-custom-object-data) | 调用本接口更新CRM自定义对象数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取自定义对象的元数据](/document/orgapp/get-metadata-description-of-crm-custom-object) | 调用本接口读取钉钉CRM自定义对象的元数据描述。 | 旧版 | 支持 | 不支持 | 不支持 |
| [根据指定条件查询自定义对象数据](/document/orgapp/retrieve-custom-crm-object-data) | 调用本接口带条件分页查询自定义对象数据。 | 旧版 | 支持 | 不支持 | 不支持 |
| [按照ID列表批量获取CRM自定义表单数据](/document/orgapp/retrieves-custom-crm-forms-from-the-id-list) | 调用本接口根据实例ID列表批量获取CRM自定义对象数据。 | 旧版 | 支持 | 不支持 | 不支持 |

### **客户群**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建客户群](/document/orgapp/create-a-customer-group) | 用于创建客户群。 | 新版 | 支持 | 支持 | 不支持 |
| [查询客户群列表](/document/orgapp/query-the-list-of-customer-groups) | 调用本接口根据指定过滤条件和排序规则，查询客户群列表数据。 | 新版 | 支持 | 支持 | 不支持 |
| [获取单个客户群详情](/document/orgapp/obtain-a-single-customer-group) | 调用本接口获取单个客户群的详情数据。 | 新版 | 支持 | 支持 | 不支持 |
| [批量查询客户群](/document/orgapp/query-customer-groups-in-batches) | 调用本接口批量查询客户群的信息。 | 新版 | 支持 | 支持 | 不支持 |
| [创建客户群组](/document/orgapp/crm-create-group) | 用于创建客户群组。 | 新版 | 支持 | 支持 | 不支持 |
| [获取单个客户群组详情](/document/orgapp/queries-the-details-of-a-single-customer-group) | 调用本接口获取单个客户群组详情。 | 新版 | 支持 | 支持 | 不支持 |
| [更新客户群组](/document/orgapp/crm-update-group) | 调用本接口更新客户群组信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [查询客户群组列表](/document/orgapp/query-groups) | 调用本接口根据指定的筛选条件和排序规则，查询客户群组列表数据。 | 新版 | 支持 | 支持 | 不支持 |

## **行业开放**

### **数字乡村**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [增加或减少居民积分](/document/orgapp/increase-or-decrease-resident-points) | 在积分管理或者全员圈场景中，可调用本接口添加居民积分。 | 新版 | 支持 | 支持 | 不支持 |
| [查询组织维度配置的所有积分规则](/document/orgapp/query-all-credit-rules) | 在全员圈和积分管理场景下，可调用本接口查询组织维度配置的的积分规则。 | 新版 | 支持 | 支持 | 不支持 |
| [分页查询居民积分流水](/document/orgapp/query-the-integral-flow-records-by-page) | 在全员圈或积分管理场景下，可调用本接口分页查询积分流水。 | 新版 | 支持 | 支持 | 不支持 |

### **地产行业**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建项目组](/document/orgapp/create-a-project-group) | 创建一个项目组。 | 新版 | 支持 | 支持 | 不支持 |
| [查询项目组信息](/document/orgapp/query-a-project-group-in-the-specified-park) | 查询指定项目组信息。 | 新版 | 支持 | 支持 | 不支持 |
| [删除项目组](/document/orgapp/delete-a-project-group) | 删除指定项目组。 | 新版 | 支持 | 支持 | 不支持 |
| [创建园区项目](/document/orgapp/create-a-campus-project) | 创建一个园区项目。 | 新版 | 支持 | 支持 | 不支持 |
| [查询园区项目信息](/document/orgapp/query-a-project-in-a-specified-campus) | 查询指定园区项目的信息。 | 新版 | 支持 | 支持 | 不支持 |

### **医疗**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [保存人员扩展属性](/document/orgapp/personnel-extension-property-error) | 支持保存人员扩展属性。 | 新版 | 支持 | 不支持 | 不支持 |

### **制造业**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [计件报工](/document/orgapp/riqing-monthly-settlement-piece-rate-reporting-interface) | 本接口用于MES系统上报计件数据到平台。 | 新版 | 支持 | 支持 | 不支持 |
| [查询计件报工数据](/document/orgapp/riqing-monthly-settlement-query-interface-for-piece-rate-reporting) | 调用本接口查询计件报工的数据。 | 新版 | 支持 | 支持 | 不支持 |

### **设备上钉**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [批量注册与激活设备](/document/orgapp/register-and-activate-devices-in-batches) | 批量注册与激活设备。 | 新版 | 支持 | 支持 | 不支持 |
| [注册设备到钉钉](/document/orgapp/pin-registration-interface) | 将设备注册到钉钉上。 | 新版 | 支持 | 支持 | 不支持 |
| [查询已经注册的设备信息](/document/orgapp/query-information-about-a-registered-device) | 分页查询已经注册的设备信息。 | 新版 | 支持 | 支持 | 不支持 |

### **服务群**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [群发任务](/document/orgapp/service-group-sending-task-interface) | 新增群发任务。 | 新版 | 支持 | 不支持 | 不支持 |
| [创建场景服务群](/document/orgapp/create-a-scenario-service-group) | 创建场景服务群。 | 新版 | 支持 | 不支持 | 不支持 |
| [更换服务群所在的群分组](/document/orgapp/modify-a-service-group) | 更换服务群所在的群分组。 | 新版 | 支持 | 不支持 | 不支持 |
| [添加服务群成员](/document/orgapp/add-service-group-members) | 将企业下成员添加到智能服务群中。 | 新版 | 支持 | 不支持 | 不支持 |
| [发送服务群消息](/document/orgapp/service-group-message-sending-interface) | 发送服务群消息。 | 新版 | 支持 | 不支持 | 不支持 |
| [查询服务群活跃用户](/document/orgapp/queries-active-service-users) | 获取指定服务群内近期活跃的用户。 | 新版 | 支持 | 不支持 | 不支持 |
| [升级云客服服务群为钉钉智能服务群](/document/orgapp/upgraded-the-cloud-customer-service-group-to-the-dingtalk-intelligent) | 将智能云客服下的服务群，升级为智能服务群中的服务群。 | 新版 | 支持 | 不支持 | 不支持 |
| [升级普通群为服务群](/document/orgapp/a-dingtalk-group-is-upgraded-to-one-of-the-intelligent) | 将企业内部群、普通群，升级为智能服务群中的服务群。 | 新版 | 支持 | 不支持 | 不支持 |

### **新教育**

#### **家校通讯录2.0**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取部门详情](/document/orgapp/obtains-queries-department-details) | 查看某个部门详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取部门列表](/document/orgapp/obtains-the-department-node-list) | 查看某个部门下的所有子部门列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取人员列表](/document/orgapp/obtains-a-list-of-home-school-user-identities) | 查看班级下的人员身份列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取人员详情](/document/orgapp/obtain-the-identity-details-of-home-school-personnel) | 查看班级下的人员详细信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取班级内学生的关系列表](/document/orgapp/queries-the-list-of-relationships) | 查看班级下的所有学生的关系列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取学生监护人详情](/document/orgapp/obtain-the-relationship-between-home-and-school-personnel) | 查看班级下某个监护人的详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [初始化家校架构](/document/orgapp/initialize-the-home-school-architecture) | 初始化家校结构。 | 新版 | 支持 | 支持 | 不支持 |
| [创建学段](/document/orgapp/create-a-learning-segment) | 在指定校区下创建学段。 | 新版 | 支持 | 支持 | 不支持 |
| [创建年级](/document/orgapp/create-grade) | 创建年级。 | 新版 | 支持 | 支持 | 不支持 |
| [创建班级](/document/orgapp/create-a-class) | 在指定的年级下创建班级。 | 新版 | 支持 | 支持 | 不支持 |
| [添加学生](/document/orgapp/add-student) | 在指定的班级下新增学生信息。 | 新版 | 支持 | 支持 | 不支持 |
| [添加家长](/document/orgapp/add-parent) | 在指定的班级下添加家长信息。 | 新版 | 支持 | 支持 | 不支持 |
| [添加老师](/document/orgapp/add-teacher) | 在指定班级下新增老师信息。 | 新版 | 支持 | 支持 | 不支持 |
| [学生调班](/document/orgapp/shift-students) | 学生调班。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除老师](/document/orgapp/delete-teacher) | 删除老师。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除学生](/document/orgapp/delete-student) | 删除学生。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除家长关系](/document/orgapp/delete-parent-relationship) | 删除与此家长关联的家长身份。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除家校部门](/document/orgapp/delete-home-school-department) | 删除家校部门。 | 旧版 | 支持 | 支持 | 不支持 |
| [创建自定义校区或部门](/document/orgapp/create-a-custom-campus-or-department) | 创建自定义校区或部门。 | 旧版 | 支持 | 支持 | 不支持 |
| [创建自定义部门下的班级](/document/orgapp/create-classes-in-a-custom-department) | 创建自定义部门下的班级。 | 旧版 | 支持 | 支持 | 不支持 |

#### **班级圈**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取班级圈话题列表](/document/orgapp/obtain-a-topic-list-of-class-circles) | 调用本接口获取班级圈话题列表。 | 旧版 | 支持 | 不支持 | 不支持 |
| [获取班级圈动态列表](/document/orgapp/dynamic-list-opening-of-class-circle) | 调用本接口获取班级圈动态列表。 | 旧版 | 支持 | 不支持 | 不支持 |

#### **数字化证书**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取数字化证书](/document/orgapp/obtain-digital-certificate) | 调用本接口获取数字化证书。 | 旧版 | 支持 | 支持 | 不支持 |

### **行业角色管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取用户所在的行业角色信息](/document/orgapp/obtain-the-industry-role-information-of-the-user) | 根据用户userId，获取员工所在的角色信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取行业角色下的用户列表](/document/orgapp/obtains-a-list-of-users-under-an-industry-role) | 根据行业角色编码获取角色下的人员列表。 | 新版 | 支持 | 支持 | 不支持 |

### **钉钉物联**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [注册设备](/document/orgapp/register-devices) | 将企业设备信息注册到钉钉物联应用。 | 新版 | 支持 | 支持 | 不支持 |
| [批量注册设备](/document/orgapp/batchregister-devices) | 批量注册设备到钉钉物联应用。 | 新版 | 支持 | 支持 | 不支持 |
| [批量修改设备](/document/orgapp/batch-modify-devices) | 修改设备信息。 | 新版 | 支持 | 支持 | 不支持 |
| [删除设备](/document/orgapp/delete-a-device) | 删除设备。 | 新版 | 支持 | 支持 | 不支持 |
| [批量注册事件类型](/document/orgapp/registration-event-type) | 将所有事件类型注册到钉钉物联应用。 | 新版 | 支持 | 支持 | 不支持 |
| [设备入会](/document/orgapp/equipment-membership) | 将设备等加入会议。 | 新版 | 支持 | 支持 | 不支持 |
| [事件推送](/document/orgapp/dingtalk-iot-push-events) | 推送事件信息。 | 新版 | 支持 | 支持 | 不支持 |

## **生态开放**

### **智能客服**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建自助单](/document/orgapp/create-a-self-service-ticket) | 创建用户自定义的自助单。 | 新版 | 支持 | 支持 | 不支持 |
| [执行工单活动](/document/orgapp/intelligent-customer-service-execute-work-order-activities) | 执行工单活动。 | 新版 | 支持 | 支持 | 不支持 |
| [查询动作记录](/document/orgapp/intelligent-customer-service-query-action-records) | 查询动作记录。 | 新版 | 支持 | 支持 | 不支持 |
| [分页查询工单](/document/orgapp/intelligent-customer-service-paging-query-work-order) | 分页查询工单。 | 新版 | 支持 | 支持 | 不支持 |

### **小蜜客服**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [智能问答](/document/orgapp/alimebot-intelligent-q-a-interface) | 使用小蜜客服机器人的能力进行智能问答。 | 新版 | 支持 | 不支持 | 不支持 |
| [推送小蜜机器人单聊O2O消息](/document/orgapp/push-xiaomi-customer-service-robot-single-chat-message) | 通过小蜜客服机器人发送O2O（即Online To Offline）线上线下消息。 | 新版 | 支持 | 不支持 | 不支持 |
| [小蜜客服机器人消息回复](/document/orgapp/xiaomi-customer-service-robot-message-reply) | 根据小蜜客服机器人sessionId进行异步消息回复。 | 新版 | 支持 | 不支持 | 不支持 |
| [查询机器人基础指标数据](/document/orgapp/query-robot-data-indicators) | 根据机器人ID查询某时间段机器人的基础指标数据。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取用户登录凭证](/document/orgapp/obtains-the-user-login-credential-of-the-third-party-system-of) | 获取用户的登录凭证。 | 新版 | 支持 | 不支持 | 不支持 |

### **AI**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [文本翻译](/document/orgapp/dingtalk-translation) | 调用本接口翻译一段文本。 | 旧版 | 支持 | 支持 | 不支持 |
| [OCR文字识别](/document/orgapp/structured-image-recognition-api) | 调用本接口进行OCR文字识别。即识别一张图片上的文字。 | 旧版 | 支持 | 支持 | 不支持 |
| [ASR 一句话语音识别](/document/orgapp/asr-short-sentence-recognition) | 调用本接口识别一段60秒内的语音。 | 旧版 | 支持 | 支持 | 不支持 |

### **员工服务台**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [使用服务助手推送消息](/document/orgapp/the-message-pushing-interface-of-the-assistant) | 通过服务助手机器人给企业员工发送消息。 | 旧版 | 支持 | 不支持 | 不支持 |

### **阿里商旅**

**城市基础数据**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [机票城市搜索](https://open.dingtalk.com/document/orgapp/air-ticket-city-search) | 搜索火车票城市。 | 旧版 | 支持 | 支持 | 不支持 |
| [火车票城市搜索](https://open.dingtalk.com/document/orgapp/train-ticket-city-search) | 搜索机票城市。 | 旧版 | 支持 | 支持 | 不支持 |

**维护成本中心和发票抬头**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [新建成本中心](https://open.dingtalk.com/document/orgapp/new-cost-center) | 新建成本中心。 | 旧版 | 支持 | 支持 | 不支持 |
| [修改成本中心](https://open.dingtalk.com/document/orgapp/modify-basic-cost-center-information) | 修改成本中心基本信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除成本中心](https://open.dingtalk.com/document/orgapp/delete-cost-center) | 删除成本中心。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询成本中心](https://open.dingtalk.com/document/orgapp/query-cost-center) | 查询成本中心信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [设置成本中心人员信息](https://open.dingtalk.com/document/orgapp/set-up-cost-center-personnel-information) | 设置成本中心人员信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除成本中心人员信息](https://open.dingtalk.com/document/orgapp/delete-cost-center-personnel-information) | 删除成本中心人员信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [商旅成本中心转换为外部成本中心](https://open.dingtalk.com/document/orgapp/business-travel-cost-center-converted-to-external-cost-center) | 商旅成本中心转换为外部成本中心。 | 旧版 | 支持 | 支持 | 不支持 |

**项目管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [添加项目](https://open.dingtalk.com/document/orgapp/add-a-project) | 添加商旅项目。 | 旧版 | 支持 | 支持 | 不支持 |
| [修改项目](https://open.dingtalk.com/document/orgapp/project-change) | 修改项目信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除项目](https://open.dingtalk.com/document/orgapp/delete-a-project) | 删除项目。 | 旧版 | 支持 | 支持 | 不支持 |

**出差申请**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [新建审批单](https://open.dingtalk.com/document/orgapp/user-new-approval-form) | 新建审批单。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取申请单列表](https://open.dingtalk.com/document/orgapp/search-enterprise-approval-form-data) | 查询企业审批单数据。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取申请单详情](https://open.dingtalk.com/document/orgapp/obtains-the-detailed-data-of-a-single-request) | 获取单个申请单的详细信息。 | 旧版 | 支持 | 支持 | 不支持 |
| [修改申请单](https://open.dingtalk.com/document/orgapp/user-modify-approval-form) | 修改出差申请单。 | 旧版 | 支持 | 支持 | 不支持 |
| [更新申请单状态](https://open.dingtalk.com/document/orgapp/update-approval-form) | 更新审批单状态。 | 旧版 | 支持 | 支持 | 不支持 |
| [搜索第三方酒店超标审批单](https://open.dingtalk.com/document/orgapp/dingtalk-oapi-alitrip-btrip-exceedapply-hotel-get) | 搜索第三方酒店超标审批单。 | 旧版 | 支持 | 支持 | 不支持 |
| [搜索第三方火车票超标审批单](https://open.dingtalk.com/document/orgapp/dingtalk-oapi-alitrip-btrip-exceedapply-train-get) | 搜索第三方火车票超标审批单。 | 旧版 | 支持 | 支持 | 不支持 |
| [回传第三方超标审批结果](https://open.dingtalk.com/document/orgapp/dingtalk-oapi-alitrip-btrip-exceedapply-sync) | 回传第三方超标审批结果。 | 旧版 | 支持 | 支持 | 不支持 |
| [搜索第三方机票超标审批单](https://open.dingtalk.com/document/orgapp/dingtalk-oapi-alitrip-btrip-exceedapply-flight) | 搜索第三方机票的超标审批单。 | 旧版 | 支持 | 支持 | 不支持 |

**订单管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [关联单号查询相关订单信息列表](https://open.dingtalk.com/document/orgapp/link-no-to-query-the-list-of-related-order-information) | 申请单中关联单号获取订单信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取企业机票订单数据](https://open.dingtalk.com/document/orgapp/obtains-enterprise-ticket-order-data) | 获取企业机票订单数据 | 旧版 | 支持 | 支持 | 不支持 |
| [获取企业商旅酒店订单数据](https://open.dingtalk.com/document/orgapp/enterprises-obtain-order-data-for-business-hotels) | 获取商旅酒店订单数据。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取企业火车票订单数据](https://open.dingtalk.com/document/orgapp/obtains-the-enterprise-train-ticket-order-data) | 获取企业火车票订单数据。 | 旧版 | 支持 | 支持 | 不支持 |
| [获取用车订单数据](https://open.dingtalk.com/document/orgapp/vehicle-order-query-interface) | 获取企业用车订单数据。 | 旧版 | 支持 | 支持 | 不支持 |

**阿里商旅跳转链接**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取商旅访问地址](https://open.dingtalk.com/document/orgapp/obtain-business-travel-access-addresses) | 获取各个场景预订访问地址，以及我的订单地址。 | 旧版 | 支持 | 支持 | 不支持 |

**发票管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [新增发票配置](https://open.dingtalk.com/document/orgapp/new-invoice-configuration) | 新增发票配置。 | 旧版 | 支持 | 支持 | 不支持 |
| [配置发票适用人群](https://open.dingtalk.com/document/orgapp/configure-invoice-users) | 配置发票适用人群。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询可用发票列表](https://open.dingtalk.com/document/orgapp/query-available-invoices) | 查询可用发票列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [修改发票配置](https://open.dingtalk.com/document/orgapp/modify-invoice-configuration) | 修改发票配置。 | 旧版 | 支持 | 支持 | 不支持 |
| [删除发票信息](https://open.dingtalk.com/document/orgapp/delete-invoice-information) | 删除发票信息。 | 旧版 | 支持 | 支持 | 不支持 |

**市内用车申请**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [同步市内用车申请单](https://open.dingtalk.com/document/orgapp/synchronize-third-party-city-vehicle-approval-form) | 同步市内用车申请单。 | 新版 | 支持 | 支持 | 不支持 |
| [审批市内用车申请单](https://open.dingtalk.com/document/orgapp/approval-of-third-party-city-car-application-form) | 审批市内用车申请单。 | 新版 | 支持 | 支持 | 不支持 |
| [查询市内用车申请单](https://open.dingtalk.com/document/orgapp/query-the-application-form-for-third-party-vehicles-in-the-city) | 查询市内用车申请单。 | 新版 | 支持 | 支持 | 不支持 |

**账单管理**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询用车结算记录](https://open.dingtalk.com/document/orgapp/query-interface-for-vehicle-settlement-and-bookkeeping) | 查询商旅用车的结算记账数据。 | 新版 | 支持 | 支持 | 不支持 |
| [查询商旅火车票结算数据](https://open.dingtalk.com/document/orgapp/business-travel-train-ticket-settlement-bookkeeping-query-interface) | 查询商旅火车票结算记账数据。 | 新版 | 支持 | 支持 | 不支持 |
| [查询酒店结算数据](https://open.dingtalk.com/document/orgapp/hotel-settlement-bookkeeping-query-interface) | 查询商旅酒店结算记账数据。 | 新版 | 支持 | 支持 | 不支持 |
| [查询机票结算数据](https://open.dingtalk.com/document/orgapp/ticket-settlement-bookkeeping-query-interface) | 查询机票结算记账数据。 | 新版 | 支持 | 支持 | 不支持 |
| [获取月对账结算数据](https://open.dingtalk.com/document/orgapp/obtain-monthly-reconciliation-settlement-data) | 获取月对账结算数据下载地址。 | 旧版 | 支持 | 支持 | 不支持 |

**预估价**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [查询预估价](https://open.dingtalk.com/document/orgapp/query-estimated-price) | 查询预估价。 | 旧版 | 支持 | 支持 | 不支持 |

### **金智CRM**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [客户资料](https://open.dingtalk.com/document/orgapp/add-or-edit-customer-profile) | 新增或编辑客户资料。 | 新版 | 支持 | 支持 | 不支持 |
| [客户公共池](https://open.dingtalk.com/document/orgapp/add-or-edit-customer-public-pools) | 新增或编辑客户公共池。 | 新版 | 支持 | 支持 | 不支持 |
| [联系人](https://open.dingtalk.com/document/orgapp/add-or-edit-contacts) | 新增或编辑联系人。 | 新版 | 支持 | 支持 | 不支持 |
| [合同订单](https://open.dingtalk.com/document/orgapp/add-or-edit-contract-orders) | 新增或编辑合同订单。 | 新版 | 支持 | 支持 | 不支持 |
| [发货单](https://open.dingtalk.com/document/orgapp/add-or-edit-invoices) | 新增或编辑发货单。 | 新版 | 支持 | 支持 | 不支持 |
| [销售换货单](https://open.dingtalk.com/document/orgapp/add-or-edit-a-sales-order) | 新增或编辑销售换货单。 | 新版 | 支持 | 支持 | 不支持 |
| [销售机会](https://open.dingtalk.com/document/orgapp/add-or-edit-opportunities) | 新增或编辑销售机会。 | 新版 | 支持 | 支持 | 不支持 |
| [报价记录](https://open.dingtalk.com/document/orgapp/add-or-edit-quotation-records) | 新增或编辑报价记录。 | 新版 | 支持 | 支持 | 不支持 |
| [采购单](https://open.dingtalk.com/document/orgapp/edit-purchase-order) | 新增或编辑采购单。 | 新版 | 支持 | 支持 | 不支持 |
| [生产单](https://open.dingtalk.com/document/orgapp/add-or-edit-a-production-order) | 新增或编辑生产单。 | 新版 | 支持 | 支持 | 不支持 |
| [产品信息](https://open.dingtalk.com/document/orgapp/add-or-edit-product-information) | 新增或编辑产品信息。 | 新版 | 支持 | 支持 | 不支持 |
| [入库单](https://open.dingtalk.com/document/orgapp/add-or-edit-a-shipment-record) | 新增或编辑入库单。 | 新版 | 支持 | 支持 | 不支持 |
| [出库单](https://open.dingtalk.com/document/orgapp/add-or-edit-an-issue-ticket) | 新增或编辑出库单。 | 新版 | 支持 | 支持 | 不支持 |
| [获取数据列表](https://open.dingtalk.com/document/orgapp/obtain-the-data-list) | 获取各种单据的列表数据。 | 新版 | 支持 | 支持 | 不支持 |
| [获取数据详情](https://open.dingtalk.com/document/orgapp/queries-data-details) | 获取各种单据的详情数据。 | 新版 | 支持 | 支持 | 不支持 |

### **氚云**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取应用列表](https://open.dingtalk.com/document/orgapp/queries-applications) | 查询氚云的应用信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取应用功能节点](https://open.dingtalk.com/document/orgapp/queries-the-application-feature-nodes) | 获取应用的功能节点信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取组织数据](https://open.dingtalk.com/document/orgapp/queries-organization-data) | 获取组织部门数据信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取用户数据](https://open.dingtalk.com/document/orgapp/obtain-user-data) | 获取用户基础数据信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取角色数据](https://open.dingtalk.com/document/orgapp/obtain-role-data) | 获取角色组、角色数据等信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取角色用户数据](https://open.dingtalk.com/document/orgapp/obtain-role-data-1) | 获取指定角色包含的用户。 | 新版 | 支持 | 支持 | 不支持 |
| [获取表单对象结构](https://open.dingtalk.com/document/orgapp/gets-the-form-object-structure) | 获取表单对象结构信息。 | 新版 | 支持 | 支持 | 不支持 |
| [创建表单业务数据](https://open.dingtalk.com/document/orgapp/create-form-business-data) | 创建单条表单、流程表单的业务数据对象。 | 新版 | 支持 | 支持 | 不支持 |
| [查询表单业务数据列表](https://open.dingtalk.com/document/orgapp/querying-form-business-data) | 查询表单业务数据实例集合。 | 新版 | 支持 | 支持 | 不支持 |
| [修改表单业务对象数据](https://open.dingtalk.com/document/orgapp/modify-form-business-object-data) | 修改表单的单条业务实例数据。 | 新版 | 支持 | 支持 | 不支持 |
| [批量新增表单业务数据](https://open.dingtalk.com/document/orgapp/batch-add-form-business-data) | 批量新增表单的业务实例数据。 | 新版 | 支持 | 支持 | 不支持 |
| [删除业务对象](https://open.dingtalk.com/document/orgapp/delete-a-business-object) | 批量新增表单的业务实例数据。 | 新版 | 支持 | 支持 | 不支持 |
| [获取业务实例信息](https://open.dingtalk.com/document/orgapp/queries-business-instance-information) | 获取表单的单条业务实例数据。 | 新版 | 支持 | 支持 | 不支持 |
| [创建流程实例](https://open.dingtalk.com/document/orgapp/create-a-process-instance) | 创建流程表单的流程实例数据。 | 新版 | 支持 | 支持 | 不支持 |
| [删除流程实例数据](https://open.dingtalk.com/document/orgapp/delete-process-instance-data) | 删除流程表单的单条流程实例数据。 | 新版 | 支持 | 支持 | 不支持 |
| [取消流程实例](https://open.dingtalk.com/document/orgapp/cancel-a-process-instance) | 取消流程实例，取消后的流程实例状态为已取消。 | 新版 | 支持 | 支持 | 不支持 |
| [查询流程实例](https://open.dingtalk.com/document/orgapp/query-flow-instances) | 查询流程表单的流程实例数据。 | 新版 | 支持 | 支持 | 不支持 |
| [查询流程实例节点工作项](https://open.dingtalk.com/document/orgapp/query-flow-instance-node-work-items) | 获取流程实例节点工作项的相关信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取附件临时访问地址](https://open.dingtalk.com/document/orgapp/obtain-the-temporary-attachment-free-address) | 获取附件临时免登的访问地址。 | 新版 | 支持 | 支持 | 不支持 |
| [获取文件上传地址](https://open.dingtalk.com/document/orgapp/obtain-the-upload-url-of-a-file-2) | 返回表单中指定图片、附件等控件的文件上传地址。 | 新版 | 支持 | 支持 | 不支持 |

### **e签宝**

**鉴权**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [e签宝数据初始化](/document/orgapp/isv-service-provider-data-initialization) | 帮助钉钉企业进行e签宝开放平台的数据初始化。 | 新版 | 支持 | 支持 | 不支持 |
| [获取授权的页面地址](/document/orgapp/obtain-the-address-of-the-authorized-page) | 获取企业授权的页面地址。 | 新版 | 支持 | 支持 | 不支持 |
| [取消企业授权](/document/orgapp/cancel-enterprise-authorization) | 取消授权过企业的授权状态。 | 新版 | 支持 | 支持 | 不支持 |

**套餐**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [套餐转售—分润模式](/document/orgapp/package-resale-1-distribution-mode) | 为使用电子合同的用户创建转售订单。 | 新版 | 支持 | 支持 | 不支持 |
| [套餐转售—底价结算模式](/document/orgapp/package-resale-2-reserve-price-settlement-mode) | 直接转售e签宝订单给最终真正使用电子合同的用户。 | 新版 | 支持 | 支持 | 不支持 |
| [查询套餐余量](/document/orgapp/query-package-balance) | 查询当前企业的套餐余量。 | 新版 | 支持 | 支持 | 不支持 |

**用户**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取企业的e签宝微应用状态](/document/orgapp/obtain-the-current-status-of-the-company-s-e-sign-micro-application) | 获取企业的e签宝微应用状态。 | 新版 | 支持 | 支持 | 不支持 |
| [查询企业是否实名认证](/document/orgapp/query-enterprise-information) | 查询企业是否已在e签宝完成实名认证。 | 新版 | 支持 | 支持 | 不支持 |
| [获取企业控制台地址](/document/orgapp/get-enterprise-console-address) | 获取的企业在e签宝的控制台地址。 | 新版 | 支持 | 支持 | 不支持 |
| [查询个人是否实名认证](/document/orgapp/query-personal-information) | 查询当前用户是否已在e签宝完成实名认证。 | 新版 | 支持 | 支持 | 不支持 |
| [获取个人实名的地址](/document/orgapp/obtain-the-address-that-is-redirected-to-the-user-s-real) | 通过个人信息接口查询到个人未实名时，可调用本接口获取个人实名认证地址。 | 新版 | 支持 | 支持 | 不支持 |
| [获取跳转到企业实名的地址](/document/orgapp/obtain-the-address-that-is-redirected-to-the-enterprise-s-real) | 通过企业信息接口查询到企业未实名时，可调用本接口获取实名地址，在应用内展示给企业。 | 新版 | 支持 | 支持 | 不支持 |

**文件**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取文件上传地址](/document/orgapp/obtain-the-upload-url-of-a-file-1) | 获取到文件上传地址。 | 新版 | 支持 | 支持 | 不支持 |
| [获取文件详情](/document/orgapp/gets-the-file-details) | 查询文件详情。 | 新版 | 支持 | 支持 | 不支持 |

**签署流程**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [获取发起签署任务的地址](/document/orgapp/obtain-the-address-used-to-initiate-a-signed-task) | 获取发起签署任务的地址。 | 新版 | 支持 | 支持 | 不支持 |
| [创建签署流程](/document/orgapp/use-the-api-to-initiate-a-signature-process) | 当ISV侧企业有文件需签署时，可调用本接口获取发起签署地址。 | 新版 | 支持 | 支持 | 不支持 |
| [获取签署人签署地址](/document/orgapp/get-signatory-address) | 获取签署人签署地址。 | 新版 | 支持 | 支持 | 不支持 |
| [获取流程的签署详情](/document/orgapp/get-the-details-of-process-signing) | 根据taskId获取流程签署相关的详细信息。 | 新版 | 支持 | 支持 | 不支持 |
| [获取流程任务用印审批列表](/document/orgapp/obtains-the-print-approval-list-for-process-tasks) | 获取流程任务用印审批列表。 | 新版 | 支持 | 支持 | 不支持 |
| [获取流程详细信息及操作记录](/document/orgapp/obtains-the-task-details) | 获取流程详细信息及操作记录。 | 新版 | 支持 | 支持 | 不支持 |
| [获取流程任务的所有合同列表](/document/orgapp/get-a-list-of-all-contracts-for-the-process-task) | 获取流程任务的所有合同列表，收到签署完成消息后查询。 | 新版 | 支持 | 支持 | 不支持 |

## 应用管理

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [创建企业内部应用H5微应用](/document/orgapp/create-an-h5-application-for-your-enterprise) | 用于创建企业内部应用H5微应用 | 新版 | 支持 | 不支持 | 不支持 |
| [更新企业内部应用H5微应用](/document/orgapp/update-internal-h5-applications) | 用本接口删除企业内部应用H5微应用。 | 新版 | 支持 | 不支持 | 不支持 |
| [删除企业内部应用H5微应用](/document/orgapp/delete-an-internal-h5-application) | 更新企业内部应用H5微应用信息。 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业所有应用列表](/document/orgapp/obtains-a-list-of-all-enterprise-applications) | 用于获取企业所有应用的信息 | 新版 | 支持 | 不支持 | 不支持 |
| [获取用户可见的企业应用列表](/document/orgapp/obtains-the-list-of-enterprise-applications-visible-to-a-user) | 用于获取用户可使用的企业应用列表及应用信息 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业内部应用的可使用范围](/document/orgapp/obtains-the-application-visible-range) | 用于更新企业内部应用微应用的可使用范围。 | 新版 | 支持 | 不支持 | 不支持 |
| [更新企业内部应用的可使用范围](/document/orgapp/update-the-visible-range-of-micro-applications) | 获取企业内部应用微应用设置的可使用范围信息。 | 新版 | 支持 | 不支持 | 不支持 |

## 数据目录接口能力

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| 新版规范（新版服务端API） | API | **规范版本** | 企业内部应用 | 第三方企业应用 | 第三方个人应用 |
| [获取企业用户激活状态统计数据](https://open.dingtalk.com/document/orgapp/obtains-statistics-on-user-activation-status) | 获取企业用户激活状态统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取数字区县组织信息](https://open.dingtalk.com/document/orgapp/querydigitaldistrictorginfo-api-reference) | 获取数字区县组织信息 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业全员圈统计数据](https://open.dingtalk.com/document/orgapp/obtains-the-statistical-data-of-all-employees-of-an-enterprise) | 获取企业全员圈统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业DING接收及评论统计数据](https://open.dingtalk.com/document/orgapp/obtain-statistics-on-receiving-and-comments-of-enterprise-ding) | 获取企业DING接收及评论统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业群聊统计数据](https://open.dingtalk.com/document/orgapp/obtain-enterprise-group-chat-statistics) | 获取企业群聊统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业用户在线统计数据](https://open.dingtalk.com/document/orgapp/retrieve-online-statistics-of-enterprise-users) | 获取企业用户在线统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业单聊统计数据](https://open.dingtalk.com/document/orgapp/queries-the-statistics-on-one-time-enterprise-chats) | 获取企业单聊统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业电话会议统计数据](https://open.dingtalk.com/document/orgapp/get-enterprise-teleconference-statistics) | 获取企业电话会议统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业视频会议统计数据](https://open.dingtalk.com/document/orgapp/get-enterprise-video-conference-statistics) | 获取企业视频会议统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业钉盘统计数据](https://open.dingtalk.com/document/orgapp/obtains-the-statistics-on-enterprise-dingtalk-trays) | 获取企业钉盘统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业日程统计数据](https://open.dingtalk.com/document/orgapp/queries-enterprise-schedule-statistics) | 获取企业日程统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业待办统计数据](https://open.dingtalk.com/document/orgapp/obtains-the-to-do-statistics-of-an-enterprise) | 获取企业待办统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业日志统计数据](https://open.dingtalk.com/document/orgapp/obtain-enterprise-log-statistics) | 获取企业日志统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业接收红包统计数据](https://open.dingtalk.com/document/orgapp/queries-the-red-envelope-receiving-statistics-of-an-enterprise) | 获取企业接收红包统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业邮箱统计数据](https://open.dingtalk.com/document/orgapp/queries-enterprise-email-statistics) | 获取企业邮箱统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业钉钉运动统计数据](https://open.dingtalk.com/document/orgapp/queries-dingtalk-movement-statistics) | 获取企业钉钉运动统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业文档统计数据](https://open.dingtalk.com/document/orgapp/get-enterprise-document-statistics) | 获取企业文档统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业签到统计数据](https://open.dingtalk.com/document/orgapp/queries-enterprise-check-in-statistics) | 获取企业签到统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业公告统计数据](https://open.dingtalk.com/document/orgapp/queries-corporate-announcement-statistics) | 获取企业公告统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业考勤统计数据](https://open.dingtalk.com/document/orgapp/queries-enterprise-attendance-statistics) | 获取企业考勤统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业审批统计数据](https://open.dingtalk.com/document/orgapp/obtains-enterprise-approval-statistics) | 获取企业审批统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业DING发送统计数据](https://open.dingtalk.com/document/orgapp/obtain-sending-statistics-of-an-enterprise-ding) | 获取企业DING发送统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业员工类型统计数据](https://open.dingtalk.com/document/orgapp/obtains-statistics-on-employee-types) | 获取企业员工类型统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业群直播统计数据](https://open.dingtalk.com/document/orgapp/obtains-the-live-stream-statistics-for-an-enterprise-group) | 获取企业群直播统计数据 | 新版 | 支持 | 不支持 | 不支持 |
| [获取企业发红包统计数据](https://open.dingtalk.com/document/orgapp/obtains-the-statistics-on-red-packets-issued-by-enterprises) | 获取企业发红包统计数据 | 新版 | 支持 | 不支持 | 不支持 |

## 智能硬件

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
| [绑定设备](/document/orgapp/establishing-a-binding-relationship-between-intelligent-hardware-and-cloud) | 调用本接口用于和组织建立绑定关系。 | 旧版 | 支持 | 支持 | 不支持 |
| [解绑设备](/document/orgapp/unbind-a-smart-hardware-device) | 调用本接口解除智能硬件设备和企业之前的绑定关系，解除绑定的数据也可以通过RDS回调开放给业务方。 | 旧版 | 支持 | 支持 | 不支持 |
| [修改设备昵称](/document/orgapp/intelligent-hardware-device-nickname-modification) | 调用本接口修改设备昵称。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询设备列表](/document/orgapp/intelligent-hardware-list-query) | 调用本接口分页查询企业下的智能设备列表。 | 旧版 | 支持 | 支持 | 不支持 |
| [查询设备详情](/document/orgapp/intelligent-hardware-device-query) | 调用本接口查询企业下的智能硬件设备详情。 | 旧版 | 支持 | 支持 | 不支持 |
| [根据设备ID查询设备](/document/orgapp/the-smart-hardware-can-query-details-based-on-the-device) | 调用本接口根据设备ID查询企业下某个智能硬件设备。 | 旧版 | 支持 | 支持 | 不支持 |

## 数据目录

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| **API** | **说明** | **规范版本** | **企业内部应用** | **第三方企业应用** | **第三方个人应用** |
|  | 调用接口获取企业用户激活状态的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取数字区县组织信息。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业全员圈评论、点赞和动态统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业接收和评论DING的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业即时沟通中群聊的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业用户在线情况的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业即时沟通中单聊的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业电话会议发起和参与情况的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业视频会议发起和参与情况的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业钉盘的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业日程的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业待办的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业日志的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业接收红包（抢红包）的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业邮箱的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业员工钉钉运动的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 获取本接口获取企业文档的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业签到的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业公告的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业考勤的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业OA审批的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业DING发送的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业花名册不同类型员工的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业群直播的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |
|  | 调用本接口获取企业发红包的统计数据。 | 新版 | 支持 | 不支持 | 不支持 |