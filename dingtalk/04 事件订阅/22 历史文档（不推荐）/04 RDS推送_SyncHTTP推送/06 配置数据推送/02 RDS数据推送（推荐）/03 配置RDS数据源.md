---
title: "配置RDS数据源"
source: "https://open.dingtalk.com/document/development/add-data-sources-for-rds"
category: "事件订阅 / 历史文档（不推荐） / RDS推送/SyncHTTP推送 / 配置数据推送 / RDS数据推送（推荐）"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-add-data-sources-for-rds_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-add-data-sources-for-rds_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-06本文介绍配置RDS数据源流程，首先购买RDS，其次配置推送表，最后配置RDS数据源。

## RDS区域选择

| 部署方式 | 支持的区域 |
| --- | --- |
| 阿里云+计算巢（推荐） | 华东1（杭州）或者华北3（张家口） |
| 聚石塔（不推荐） | 华北3（张家口） |
| 钉钉云（不推荐） | 华东1（杭州） |

**重要**

RDS的版本必须是**5.7**或**5.6**。

## 计算巢配置RDS数据源

1. 应用部署页选择部署方式是以下任意一种方式时，详情请参考文档[计算巢应用部署](/document/isv/deploy-applications-1#topic-2143805)。

   ![[development-add-data-sources-for-rds_p421609.png]]
2. 将RDS关联到计算巢应用。

   **说明**

   选择RDS时，需同时满足以下要求：

   * 必须是华东1（杭州）或者华北3（张家口）区域。
   * RDS的版本是5.x版本。

   1. 在应用部署详情页，单击"资源管理"。

      ![[development-add-data-sources-for-rds_p359136.png]]
   2. 在关联计算巢应用详情页，默认为产品方案商创建一个区域为张家口的应用分组“生产环境-张家口”。

      ![[development-add-data-sources-for-rds_p359141.png]]
   3. 如需新增或修改区域，同样点击右上角的“编辑应用分组”按钮。如图所示新增或删除区域，双击已有标签，则可修改地域，点击新增地域，可新建地域，完成后点击“确认”按钮。

      ![[development-add-data-sources-for-rds_p359153.png]]
   4. 从**产品**列表中，选择**云数据库RDS等资源**，并点击确定。

      ![[development-add-data-sources-for-rds_p359166.png]]
3. 在应用部署详情页，单击**配置**。

   ![[development-add-data-sources-for-rds_p422213.png]]
4. 在RDS列表页，单击**配置**，输入RDS的账号密码，点击确认。

   **说明**

   点击确认前需检查以下内容：

   * RDS的数据安全性中，在【钉钉推送的IP白名单】选择以下任一地址添加：

     + 华北3（张家口）RDS：100.104.69.0/24。
     + 华东1（杭州）RDS：100.104.136.0/24。
   * RDS版本为5.6或5.7版本。
   * RDS已完成[配置RDS推送表](/document/isv/configure-rds-push-table#topic-2199103)。

![[development-add-data-sources-for-rds_p420683.png]]

## 聚石塔配置RDS数据源

**说明**

已入驻聚石塔的应用，可以在聚石塔配置RDS数据源。新应用无法入驻聚石塔，部署方式请选择计算巢。

1. 完成聚石塔账号绑定，在钉钉业务域下的vpc完成RDS购买，详情请参考文档[入驻聚石塔](/document/isv/create-tmallcloud-account#topic-2024390)。
2. 完成聚石塔RDS配置，详情请参考文档[使用聚石塔RDS数据库](/document/isv/use-tmallcloud-rds#topic-2024412)。
3. 登录开发者后台，选择聚石塔 > 云推送数据源。找到已创建的RDS实例，然后单击设置。

   ![[development-add-data-sources-for-rds_p422214.png]]
4. 输入MySQL实例的账号和密码，单击确定完成添加。