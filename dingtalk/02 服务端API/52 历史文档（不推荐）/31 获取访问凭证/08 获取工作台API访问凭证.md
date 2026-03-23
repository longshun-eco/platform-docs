---
title: "获取工作台API访问凭证"
source: "https://open.dingtalk.com/document/development/used-to-obtain-the-application-authorization-without-api-token"
category: "服务端API / 历史文档（不推荐） / 获取访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-used-to-obtain-the-application-authorization-without-api-token_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-used-to-obtain-the-application-authorization-without-api-token_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-08API Token是由钉钉开放平台颁发，用来调用钉钉开放平台提供的应用管理能力。在调用钉钉开放平台提供的应用管理能力前，请参考本文先获取访问凭证API Token。

## 简介

在调用DingTalk OpenAPI中的工作台相关接口前，必须从开放平台获取访问凭证API Token，这个访问凭证包含你的企业信息以及可调用的接口权限，目前可调用工作台相关的接口如下：

* [获取工作台插件检验的规则信息](/document/dashboard/you-can-call-this-operation-to-obtain-the-information-about#doc-api-dingtalk-GetPluginRuleCheckInfo)
* [获取工作台插件权限点](/document/dashboard/obtain-the-permissions-of-the-workbench-plug-in#doc-api-dingtalk-GetPluginPermissionPoint)

## 获取访问凭证API Token

通过以下步骤，获取API Token：

1. 登录[开发者后台](https://open-dev.dingtalk.com/)。
2. 在开发者后台首页，单击**生成TOKEN**，用于生成持久的API Token。

   **说明**
   * 重新生成API Token之后，之前的API Token会失效。
   * 同一企业同一时间生效的API Token只有一个。

   ![[development-used-to-obtain-the-application-authorization-without-api-token_p290038.png]]
3. （可选）生成Token后，单击后面的设置图标，设置Token的IP白名单。

   **说明**

   出于安全性考虑，钉钉开放平台提供了生成Token和设置Token生效的IP白名单功能，降低了因Token泄漏导致的安全风险。

   ![[development-used-to-obtain-the-application-authorization-without-api-token_p290039.png]]