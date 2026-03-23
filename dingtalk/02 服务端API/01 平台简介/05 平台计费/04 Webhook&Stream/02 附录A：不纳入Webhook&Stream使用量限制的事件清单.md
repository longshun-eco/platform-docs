---
title: "附录A：不纳入Webhook&Stream使用量限制的事件清单"
source: "https://open.dingtalk.com/document/development/appendix-a-list-of-events-not-included-in-webhook"
category: "服务端API / 平台简介 / 平台计费 / Webhook&Stream"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-appendix-a-list-of-events-not-included-in-webhook_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-appendix-a-list-of-events-not-included-in-webhook_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-10为保障自建应用最基本的使用，通讯录相关事件推送次数不作使用量限制。本文介绍了不纳入每月 Webhook&Stream 使用量限制的事件清单。

## 通讯录相关事件

|  |  |
| --- | --- |
| **事件类型** | **说明** |
| user\_add\_org | 通讯录用户增加 |
| user\_modify\_org | 通讯录用户更改 |
| user\_leave\_org | 通讯录用户离职 |
| user\_active\_org | 加入企业后用户激活 |
| org\_dept\_create | 通讯录企业部门创建 |
| org\_dept\_modify | 通讯录企业部门修改 |
| org\_dept\_remove | 通讯录企业部门删除 |
| org\_change | 企业信息发生变更 |
| label\_user\_change | 员工角色信息发生变更 |
| label\_conf\_add | 增加角色或者角色组 |
| label\_conf\_del | 删除角色或者角色组 |
| label\_conf\_modify | 修改角色或者角色组 |
| org\_admin\_add | 通讯录用户被设为管理员 |
| org\_admin\_remove | 通讯录用户被取消设置管理员 |
| industry\_medical\_user\_add | 医疗通讯录用户新增 |
| org\_annual\_certification\_submission | 组织年检认证提交 |

## **医疗通讯录事件**

|  |  |
| --- | --- |
| **事件类型** | **说明** |
| industry\_medical\_dept\_event | 医疗行业科室医疗组变动 |
| industry\_medical\_dept\_prop\_event | 医疗行业科室医疗组属性变动 |
| industry\_medical\_user\_prop\_event | 医疗行业用户属性变动 |
| industry\_medical\_user\_dept\_event | 医疗行业用户所在科室医疗组变动 |
| industry\_medical\_full\_sync | 医疗通讯录全量同步 |
| industry\_medical\_user\_add | 医疗通讯录用户新增 |