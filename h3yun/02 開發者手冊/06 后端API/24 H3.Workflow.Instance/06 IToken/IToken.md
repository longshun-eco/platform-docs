---
title: "IToken"
source: "https://help.h3yun.com/contents/688/752.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance / IToken"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : IToken
说明 : 步骤类，每经历一个活动就生成一个步骤对象。一个流程模板有N个活动，一个流程实例经历了M个活动，可能是：M大于N或者M等于N或者M小于N，因为一个活动可能会经历0-k次，那么，这个流程实例的步骤对象的数量等于M。 属性 : 

| 名称 | 说明 |
| --- | --- |
| TokenId | TokenId |
| Activity | 活动 |
| SkippedExecution | 是否跳过的执行 |
| Approval | 是否同意 |
| Retrievable | 在该步是否能被取回 |
| Exceptional | 是否异常 |
| CreatedTime | 创建时间 |
| PreTokens | 前活动对应的TokenId |
| Participants | 参与者，该参与者是激活活动的时候指定的参与者 |
| FinishedTime | 完成时间 |
| State | 状态 |
| UsedTime | 使用的时间

 |