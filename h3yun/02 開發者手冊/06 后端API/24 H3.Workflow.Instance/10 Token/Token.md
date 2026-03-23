---
title: "Token"
source: "https://help.h3yun.com/contents/692/766.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance / Token"
updated: 2025-12-14
tags:
  - h3yun
  - 開發者手冊
---
类名 : Token
说明 : 步骤类，每经历一个活动就生成一个步骤对象。一个流程模板有N个活动，一个流程实例经历了M个活动，可能是：M大于N或者M等于N或者M小于N，因为一个活动可能会经历0-k次，那么，这个流程实例的步骤对象的数量等于M。 属性 : 

| 名称 | 说明 |
| --- | --- |
| TokenId | 令牌的ID |
| Activity | 该令牌对应的活动的名称 |
| Approval | 审批结果 |
| SkippedExecution | 是否是跳过的，比如：当前活动没有处理人，那么可以跳过这个活动，或者这个活动是连接点活动 |
| Exceptional | 该步骤中是否出现了异常 |
| Retrievable | 该步骤是否可以被取回，如果该属性为true，那么前一个步骤允许取回，即允许取消掉该步骤，然后重新激活上一个步骤 |
| CreatedTime | 创建时间 |
| PreTokens | 前驱令牌ID |
| FinishedTime | 完成时间 |
| State | 令牌的当前状态，运行或者结束 |
| Participants | 获取或设置活动参与者，该参与者是激活活动的时候指定的参与者 |
| UsedTime | 使用的时间，物理时间 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| UnspecifiedId | 这是一个不存在的TokenId，通常用于查询，表示表限制是哪个TokenId |
| InitialTokenId | 初始的TokenId |
| PropertyName\_TokenId | 属性名称 |
| PropertyName\_Activity | 属性名称 |
| PropertyName\_Approval | 属性名称 |
| PropertyName\_SkippedExecution | 属性名称 |
| PropertyName\_Exceptional | 属性名称 |
| PropertyName\_Retrievable | 属性名称 |
| PropertyName\_CreatedTime | 属性名称 |
| PropertyName\_PreTokens | 属性名称 |
| PropertyName\_FinishedTime | 属性名称 |
| PropertyName\_State | 属性名称 |
| PropertyName\_Participants | 属性名称 |
| PropertyName\_UsedTime | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Int32,System.String,System.Int32\[\],System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "tokenId" | 令牌Id |
| "activity" | 活动名称 |
| "preTokens" | 令牌的前驱数组，可以通过前驱获得之前的令牌和执行信息，以便于打回或者回滚 |
| "participants" | 活动的参与者 |
| 返回值 |  |
| |  |


方法名称 : IsPreToken(System.Int32)

| 参数 | 说明 |
| --- | --- |
| "tokenId" | 令牌Id |
| 返回值 |  |
| 如果是前驱令牌，则返回true |  |