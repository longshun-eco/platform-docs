---
title: "ResponseContext"
source: "https://help.h3yun.com/contents/602/699.html"
category: "開發者手冊 / 后端API / H3.SmartForm / ResponseContext"
updated: 2025-12-19
tags:
  - h3yun
  - 開發者手冊
---
类名 : ResponseContext
说明 : 返回到前端的基础类 属性 : 

| 名称 | 说明 |
| --- | --- |
| Successful | 获取或设置操作是否成功 |
| IsMobile | 是否移动表单 |
| Errors | 获取或设置错误消息的集合 |
| Message | 获取或设置需要通知前端的消息 |
| Infos | 后台返回到前台的提示信息，不同于Errors。 例如提交规则校验不通过等，不能算作异常处理 |
| DebugTrack | 调试日志信息 |
| ChangeSet | 需要变更的流程实例 |
| IsExternalForm | 是否外链表单 |
| ExternalFormUrl | 外链表单地址 |
| RecentChange | 需要Recent更新的对象 |



方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | 对象的名称 |
| 返回值 |  |
| 键值对 |  |