---
title: "获取应用的API访问凭证"
source: "https://open.dingtalk.com/document/development/used-application-authorization"
category: "服务端API / 获取访问凭证"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-used-application-authorization_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-used-application-authorization_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22本文适用于企业内部自建应用和第三方企业应用，开发者在调用钉钉开放平台OpenAPI前，需先获取应用的访问凭证（accessToken）。该凭证是调用大多数服务端API的身份凭据，有效期为2小时，建议缓存并定期刷新以保障接口调用稳定性。

## 步骤一：创建钉钉应用

1. 登录[钉钉开发者后台](https://open-dev.dingtalk.com/#/corpeapp)。
2. 单击应用开发，创建企业内部应用或第三方企业应用。
3. 在应用详情页获取应用的Client ID（原应用AppKey/SuiteKey） 和 Client Secret（原应用AppSecret/SuiteSecret）。

   ![[development-used-application-authorization_p739907.png]]

## 步骤二：获取应用的访问凭证

调用[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)接口或[获取第三方应用授权企业的accessToken](/document/development/obtain-the-access-token-of-the-authorized-enterprise-1)接口生成accessToken。