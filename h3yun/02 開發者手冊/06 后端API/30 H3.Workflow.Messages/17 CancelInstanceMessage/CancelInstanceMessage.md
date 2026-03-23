---
title: "CancelInstanceMessage"
source: "https://help.h3yun.com/contents/754/648.html"
category: "開發者手冊 / 后端API / H3.Workflow.Messages / CancelInstanceMessage"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : CancelInstanceMessage
说明 : 发送给流程，取消该流程 属性 : 

| 名称 | 说明 |
| --- | --- |
| Recursive | 是否递归取消，如果是的话，则他还会递归取消他的子流程 |



构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | 流程实例的ID |
| "recursive" | 是否进行递归的取消 |
| 返回值 |  |
| |
 |