---
title: "GitLab机器人"
source: "https://open.dingtalk.com/document/dingstart/gitlab-robot"
category: "新手指南 / 开发机器人应用 / 自定义机器人 / 第三方机器人工具接入"
updated: 
tags:
  - dingtalk
  - 新手指南
---
![[dingstart-gitlab-robot_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[dingstart-gitlab-robot_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-25本文介绍如何在钉钉群添加一个GitLab机器人进行消息推送。

## 步骤一：获取GitLab机器人Webhook地址

1. 以PC端为例，打开PC端钉钉，进入**机器人管理**页面。

   1. 选择需要添加机器人的群聊，然后依次单击**群设置** > **智能群助手**。

      ![[dingstart-gitlab-robot_p232816.png]]
   2. 点击**添加机器人**，进入**机器人管理**页面。

      ![[dingstart-gitlab-robot_p185964.png]]
2. 在**机器人管理**页面选择**GitLab**机器人，然后点击**添加**。

   ![[dingstart-gitlab-robot_p185954.png]]
3. 输入机器人名字后，点击**完成**。

   ![[dingstart-gitlab-robot_p185950.png]]
4. 复制出机器人的Webhook地址，可用于向这个群发送消息，格式如下：

   ```
   https://oapi.dingtalk.com/robot/send?access_token=XXXXXX
   ```

   **重要**

   请保管好此Webhook 地址，不要公布在外部网站上，泄露后有安全风险。

   ![[dingstart-gitlab-robot_p185951.png]]

## 步骤二：在GitLab中设置项目的Webhook

1. 进入你的 GitLab 项目，依次点击右侧**Settings** > **Webhook****s**添加Webhook。

   ![[dingstart-gitlab-robot_p131233.jpeg]]
2. 填入对应GitLab机器人的Webhook地址，即可完成配置。

   ![[dingstart-gitlab-robot_p131234.jpeg]]