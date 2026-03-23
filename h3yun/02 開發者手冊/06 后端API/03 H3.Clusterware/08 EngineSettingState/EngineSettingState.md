---
title: "EngineSettingState"
source: "https://help.h3yun.com/contents/330/334.html"
category: "開發者手冊 / 后端API / H3.Clusterware / EngineSettingState"
updated: 2025-12-17
tags:
  - h3yun
  - 開發者手冊
---
类名 : EngineSettingState
说明 : 引擎被设置的状态 
成员 : 

| 名称 | 说明 |
| --- | --- |
| Disabled | 禁用状态。某个禁用的逻辑单元，依然可以通过调用Mount方法加载到运行态中，也就是说处于运行态，但是数据库里记录的状态是禁用状态 |
| Running | 运行状态。某个运行的逻辑单元，依然可以通过调用Unmount方法卸载，也就是说处于Suspended状态，但是在数据库里记录的状态是Running状态 |
| Allocatable | 可分配状态，可以分配某个新建的逻辑单元 |
| Delayed | 延迟加载，在系统加载的时候，不会加载这个状态的逻辑单元 |
| Suspended | 实体中不存在这个状态，当Running状态的逻辑单元被卸载了，那么就处于该状态 |