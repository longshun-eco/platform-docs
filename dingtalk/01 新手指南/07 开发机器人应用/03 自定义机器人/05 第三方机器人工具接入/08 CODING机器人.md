---
title: "CODING机器人"
source: "https://open.dingtalk.com/document/dingstart/coding-robot"
category: "新手指南 / 开发机器人应用 / 自定义机器人 / 第三方机器人工具接入"
updated: 
tags:
  - dingtalk
  - 新手指南
---
![[dingstart-coding-robot_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[dingstart-coding-robot_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-25

## 生成 CODING 机器人 Webhook

从 PC 端或者手机端的群机器人入口进入到机器人管理页面，选择「CODING 机器人」，按照设置流程生成 CODING 机器人，即可获取到相应群的 Webhook，其格式如下：

```
https://oapi.dingtalk.com/robot/send?access_token=xxxxxxxx
```

## 在 CODING 中设置项目的 Webhook

1. 进入你的 CODING 项目，依次点击左侧「设置」>「Webhook」> 「新建 Webhook」来添加 Webhook

   ![[dingstart-coding-robot_p131243.png]]
2. 填入 Webhook 地址，内容格式选择「钉钉」，内容类型选择「application/json」，勾选相应的监听事件，点击「新建 Webhook」按钮即可

   ![[dingstart-coding-robot_p131244.png]]

立即去配置：<https://coding.net>