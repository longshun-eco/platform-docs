---
title: "JIRA机器人"
source: "https://open.dingtalk.com/document/dingstart/the-jira-robot"
category: "新手指南 / 开发机器人应用 / 自定义机器人 / 第三方机器人工具接入"
updated: 
tags:
  - dingtalk
  - 新手指南
---
![[dingstart-the-jira-robot_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[dingstart-the-jira-robot_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-25本文介绍如何在钉钉群添加一个JIRA机器人进行消息推送。

## 注意事项

目前JIRA机器人只支持**jira:issue\_created**和**jira:issue\_updated**事件。

## 步骤一：获取JIRA机器人Webhook地址

1. 以PC端为例，打开PC端钉钉，进入**机器人管理**页面。

   1. 选择需要添加机器人的群聊，然后依次点击**群设置** > **智能群助手**。

      ![[dingstart-the-jira-robot_p232816.png]]
   2. 点击**添加机器人**，进入**机器人管理**页面。

      ![[dingstart-the-jira-robot_p185964.png]]
2. 在**机器人管理**页面选择**JIRA**机器人，然后点击**添加**。

   ![[dingstart-the-jira-robot_p185966.png]]
3. 输入机器人名字后，点击**完成**。

   ![[dingstart-the-jira-robot_p185323.png]]
4. 复制出机器人的Webhook地址，可用于向这个群发送消息，格式如下：

   ```
   https://oapi.dingtalk.com/robot/send?access_token=XXXXXX
   ```

   **重要**

   请保管好此Webhook 地址，不要公布在外部网站上，泄露后有安全风险。

   ![[dingstart-the-jira-robot_p185980.png]]

## 步骤二：在JIRA中设置项目的Webhook

在JIRA系统中，通过**设置** > **System** > **Webhooks**进入Webhook设置页面，为相应的项目设置钉钉群机器人的Webhook，具体操作如下图所示。

1. 点击**System**菜单

   ![[dingstart-the-jira-robot_p131237.jpeg]]
2. 选择**Webhooks**设置项。

   ![[dingstart-the-jira-robot_p131238.jpeg]]
3. 新增项目**WebHook**。

   ![[dingstart-the-jira-robot_p131239.jpeg]]
4. 填写钉钉群聊天机器人Webhook。

   ![[dingstart-the-jira-robot_p131240.jpeg]]