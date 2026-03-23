---
title: "关于停止新增应用接入RDS推送服务的公告"
source: "https://open.dingtalk.com/document/development/announcement-on-stopping-new-applications-from-accessing-rds-push-service"
category: "服务端API / 平台公告"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-announcement-on-stopping-new-applications-from-accessing-rds-push-service_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-announcement-on-stopping-new-applications-from-accessing-rds-push-service_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-17本文介绍了停止新增应用接入 RDS 的推送说明和注意事项。

## **一、详细说明**

鉴于当前 RDS 推送效率低、大并发下延迟大，自 **2024** 年 **7** 月 **24** 日起，钉钉开放平台将**停止新增应用**接入 RDS 推送服务。这一调整**不影响现存**已成功对接RDS推送服务的应用程序，确保业务连续性与稳定性不受干扰。

### **具体原因**

由于 RDS 数据库配置的 IP 白名单机制，导致当流量较大时，钉钉开放平台无法通过服务器扩容来提升推送效率（扩容后的服务器不在 IP 白名单内，无法访问第三方企业应用的 RDS 数据库）。导致推送进程受阻，进而影响到事件推送的时效性。

## **二、变更影响**

仅影响新增应用接入 RDS 推送服务。不影响已接入 RDS 推送服务的应用程序。

## **三、常见问题**

* **2024 年 7 月 24 日后，我想订阅事件该怎么订阅?**

  答：你可以使用 [Stream 推送](https://open.dingtalk.com/document/isvapp/configure-stream-push)或 [SyncHTTP 推送](https://open.dingtalk.com/document/isvapp/configure-synchttp-event-push)，并强烈建议优先采用[Stream 推送](https://open.dingtalk.com/document/isvapp/configure-stream-push)方式，以实现数据传输的即时性与流畅度最大化，并实现更高的内网安全性。

**钉钉开放平台团队**

**2024年7月22日**