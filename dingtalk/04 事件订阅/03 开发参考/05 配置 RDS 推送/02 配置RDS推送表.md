---
title: "配置RDS推送表"
source: "https://open.dingtalk.com/document/development/configure-an-rds-push-table"
category: "事件订阅 / 开发参考 / 配置 RDS 推送"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-configure-an-rds-push-table_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-configure-an-rds-push-table_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22本文档适用于使用钉钉开放平台的**第三方企业应用**开发者，指导如何在阿里云计算巢环境中配置RDS数据库以接收钉钉事件推送数据。操作需具备阿里云RDS管理权限，并了解钉钉事件订阅机制。

## 准备工作

在开始配置前，请确保已完成以下准备工作：

* 已注册阿里云账号并完成实名认证。
* 已开通计算巢服务（CloudNest）权限。
* 具备RDS实例购买和管理权限。
* 已创建钉钉第三方企业应用，并完成事件订阅配置。
* 明确部署区域：推荐选择“阿里云+计算巢”模式，支持华东1（杭州）或华北3（张家口）。

## **操作步骤**

### **确定RDS区域与版本**

根据部署方式选择合适的地域：

**说明**

RDS的版本必须是**5.7**或**5.6**。

|  |  |
| --- | --- |
| 部署方式 | 支持的区域 |
| 阿里云+计算巢（推荐） | 华东1（杭州）、华北3（张家口） |
| 聚石塔（不推荐） | 华北3（张家口） |
| 钉钉云（不推荐） | 华东1（杭州） |

### **登录阿里云控制台**

访问 [阿里云控制台](https://rdsnext.console.aliyun.com/dashboard/cn-hangzhou)，登录后准备创建实例。

![[development-configure-an-rds-push-table_p421651.png]]

### **创建RDS实例**

1. 在阿里云控制台购买 **MySQL类型** 的RDS实例，建议选择高可用版以保障稳定性。

   ![[development-configure-an-rds-push-table_p420785.png]]
2. 在[RDS实例列表](https://rdsnext.console.aliyun.com/rdsList/cn-zhangjiakou/basic)页面，单击已购买的RDS实例ID链接。

   ![[development-configure-an-rds-push-table_p1047319.png]]

### **创建推送数据库**

1. 在RDS实例详情页面，单击 **数据库管理**，然后单击 **创建数据库**。
2. 创建名为`ding_cloud_push`的数据库，用于接收钉钉事件推送数据。

   ![[development-configure-an-rds-push-table_p422193.png]]

### **配置数据库账号**

1. 创建专用数据库账号（建议命名为`dinguser`）。
2. 授予该账号对`ding_cloud_push`数据库的 **读写权限**（包括SELECT、INSERT、UPDATE、DELETE等）。

   ![[development-configure-an-rds-push-table_p420758.png]]

   ![[development-configure-an-rds-push-table_p422209.png]]

### 修改字符集参数

RDS默认字符集为`utf8`，无法完整支持Emoji等四字节字符。请修改以下参数以启用 `utf8mb4` 编码：

1. 在实例详情页，单击 **参数设置**。
2. 找到并修改以下参数：

   ![[development-configure-an-rds-push-table_p422210.png]]

   * 将`character_set_server` 参数值改为 **utf8mb4**。
   * 将`character_set_filesystem` 参数值设为 **utf8**。
3. 单击 **提交参数** 使更改生效。

### 配置白名单以允许钉钉访问

为确保钉钉服务可连接至您的RDS实例，需将钉钉出口IP段加入白名单分组：

1. 在实例详情页，单击 **数据安全性**。
2. 单击 **添加白名单分组**，根据所在区域添加对应IP段：

   ![[development-configure-an-rds-push-table_p422211.png]]

   * **华北3（张家口）**：添加 `100.104.69.0/24`
   * **华东1（杭州）**：添加 `100.104.136.0/24`

### 登录数据库并执行建表SQL

1. 单击 **数据库连接**，再单击 **登录数据库**。
2. 在弹出页面输入数据库账号（如`dinguser`）和密码，通过DMS登录数据库。

   > **说明：**若出现DMS登录失败，请参考官方文档：[登录数据库](/document/service-support/log-on-to-the-database)。
3. 在数据库管理界面，打开刚创建的`ding_cloud_push`数据库。
4. 进入SQL操作界面，执行以下SQL语句创建两张推送表：

   * **open\_sync\_biz\_data**：用于接收高优先级事件的推送信息。
   * **open\_sync\_biz\_data\_medium**：用于接收低优先级事件的推送信息。

     ```javascript
     CREATE TABLE `open_sync_biz_data` (
       `id` bigint(20) NOT NULL AUTO_INCREMENT COMMENT 'ID',
       `gmt_create` datetime NOT NULL COMMENT '创建时间',
       `gmt_modified` datetime NOT NULL COMMENT '更新时间',
       `subscribe_id` varchar(64) NOT NULL COMMENT '订阅方ID',
       `corp_id` varchar(64) NOT NULL COMMENT '企业ID',
       `biz_id` varchar(128) NOT NULL COMMENT '业务ID',
       `biz_type` int(11) NOT NULL COMMENT '业务类型',
       `biz_data` text NOT NULL COMMENT '业务数据',
       `open_cursor` bigint(20) NOT NULL COMMENT '对账游标',
       `status` int(11) NOT NULL COMMENT '处理状态0为未处理。其他状态开发者自行定义',
       PRIMARY KEY (`id`),
       UNIQUE KEY `uk_subscribe_corp_biz` (`subscribe_id`,`corp_id`,`biz_id`,`biz_type`) USING BTREE
     ) ENGINE=InnoDB AUTO_INCREMENT=0 DEFAULT CHARSET=utf8mb4 COMMENT='高优先级数据';

     CREATE TABLE `open_sync_biz_data_medium` (
       `id` bigint(20) NOT NULL AUTO_INCREMENT COMMENT 'ID',
       `gmt_create` datetime NOT NULL COMMENT '创建时间',
       `gmt_modified` datetime NOT NULL COMMENT '更新时间',
       `subscribe_id` varchar(64) NOT NULL COMMENT '订阅方ID',
       `corp_id` varchar(64) NOT NULL COMMENT '企业ID',
     ```

## 注意事项

* 建议定期清理已处理的数据表记录，避免数据膨胀影响性能。
* 生产环境建议开启RDS审计日志以便追踪异常访问。
* 不要将数据库账号信息硬编码在代码中，建议使用阿里云KMS或ACM进行安全管理。
* 修改RDS参数后需重启实例的部分参数不会在此流程涉及，当前仅需修改字符集相关项即可。

## 常见问题

### Q1: DMS登录数据库失败怎么办？

A: 请检查网络连通性、账号密码正确性以及白名单是否已正确配置。参考文档：[登录数据库](/document/service-support/log-on-to-the-database)

### Q2: SQL执行报错“Access denied”？

A: 确认数据库账号具有`ding_cloud_push`库的DDL权限（CREATE TABLE等），请联系RDS管理员赋权。

### Q3: 如何确认事件已成功推送到RDS？

A: 观察`open_sync_biz_data`或`open_sync_biz_data_medium`表中是否有新增记录；也可结合钉钉事件订阅日志排查。

### Q4: 为什么接收到的数据乱码或缺少Emoji？

A: 请确认`character_set_server`已设置为`utf8mb4`，且客户端连接时也使用该字符集。