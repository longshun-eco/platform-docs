---
title: "根据unionId获取客户信息流程"
source: "https://open.dingtalk.com/document/development/retrieves-customer-information-based-on-the-union-id"
category: "服务端API / 客户管理（官方CRM） / 使用教程"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-retrieves-customer-information-based-on-the-union-id_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-retrieves-customer-information-based-on-the-union-id_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-09本文档介绍了如何调用客户管理相关接口实现获取客户信息的相关流程。首先创建一个企业内部应用，再使用客户管理提供的API和钉钉统一授权套件，实现获取客户信息流程。

## 流程简介

步骤一：登录[开发者后台](https://open-dev.dingtalk.com/#/)，创建[企业内部应用](/document/app/create-orgapp#topic-2024342)。

步骤二：获取AppKey和AppSecret。

步骤三：[申请客户管理接口权限](/document/orgapp-server/apply-for-crm-api-permission#topic-2042243)，申请相应的权限。

步骤四：获取应用访问凭证[获取企业内部应用的accessToken](/document/orgapp-server/obtain-the-access_token-of-an-internal-app#topic-2056397)。

步骤五：调用服务端客户管理相关API。

1. 调用服务端API-[创建客户群组](/document/orgapp-server/crm-create-group#doc-api-dingtalk-CreateGroupSet)接口，创建企业客户群组，获取加入该群组的邀请链接。
2. 根据加入群组的邀请链接，客户添加进该群组内的客户群，并通过公告的方式展示企业系统页面。
3. 企业系统页面使用[钉钉统一授权套件](/document/orgapp-server/instructions-for-use#topic-2084883)功能，获取访问该页面的用户unionId。
4. 根据unionId，调用服务端API-[查询客户数据](/document/orgapp-server/querying-customer-data#topic-2209865)接口，获取访问系统页面的客户详情信息。

## 步骤一：创建企业内部应用

1. 登录[开发者后台](https://open-dev.dingtalk.com/#/)，创建[企业内部应用](/document/app/create-orgapp#topic-2024342)。

   ![[development-retrieves-customer-information-based-on-the-union-id_p524152.png]]
2. 填写应用的基本信息，然后单击**确定创建**。

   * 应用类型：选择H5微应用。
   * 开发方式：选择企业自主开发。

## 步骤二：获取AppKey和AppSecret

获取AppKey和AppSecret。

![[development-retrieves-customer-information-based-on-the-union-id_p524153.png]]

## 步骤三：添加接口权限

[申请客户管理接口权限](/document/orgapp-server/apply-for-crm-api-permission#topic-2042243)，申请相应权限。

## 步骤四：获取应用访问凭证accessToken。

根据步骤二中的AppKey和AppSecret，获取应用访问凭证[获取企业内部应用的accessToken](/document/orgapp-server/obtain-the-access_token-of-an-internal-app#topic-2056397)。

## 步骤五：调用服务端客户管理相关API。

1. 调用服务端API-[创建客户群组](/document/orgapp-server/crm-create-group#doc-api-dingtalk-CreateGroupSet)接口，创建企业客户群组，获取加入该群组的邀请链接。
2. 根据加入群组的邀请链接，客户添加进该群组内的客户群，并通过公告的方式展示企业系统页面。
3. 企业系统页面使用[钉钉统一授权套件](/document/orgapp-server/instructions-for-use#topic-2084883)功能，获取访问该页面的用户unionId。
4. 根据unionId，调用服务端API-[查询客户数据](/document/orgapp-server/querying-customer-data#topic-2209865)接口，获取访问系统页面的客户详情信息。