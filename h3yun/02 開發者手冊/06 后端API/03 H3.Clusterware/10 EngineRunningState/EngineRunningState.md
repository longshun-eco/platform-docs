---
title: "EngineRunningState"
source: "https://help.h3yun.com/contents/332/336.html"
category: "開發者手冊 / 后端API / H3.Clusterware / EngineRunningState"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : EngineRunningState
说明 : 引擎所处于的状态。 
成员 : 

| 名称 | 说明 |
| --- | --- |
| Stopped | 非活动状态 |
| Starting | 启动中 |
| Running | 活动状态 |
| Stopping | 关闭中 |
| Idle | 对于EngineConfig.State==Allocatable的引擎，加载到内存中后就是这个状态 |