---
title: "UserMessage"
source: "https://help.h3yun.com/contents/669/754.html"
category: "開發者手冊 / 后端API / H3.Notification / UserMessage"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : UserMessage
说明 : 用户消息 属性 : 

| 名称 | 说明 |
| --- | --- |
| Type | 类型 |
| SenderId | 发送方，如果发送方是组织结构中的成员，那么可以在该字段中标注发送方的ID |
| ReceiverId | 接收方，如果要发送的目标是组织结构中的一个成员，则可以启用该字段，通知处理器，会自动去获得接收方的地址 |
| ReceiverAddress | 接收方地址 |
| Title | 通知的主题 |
| Content | 通知的内容 |
| LinkContent | 链接的内容 |
| PictureUrl | 获取或设置图片的URL |
| SendTime | 发送时间 |
| State | 状态，该状态字段标记通知已经被处理、或者没有被处理之类的 |
| AppCode | 应用编码 |
| SolutionCode | 应用编码 |
| BatchId | 批次推送消息的批次的Id |
| ReplyAddress | 回信地址(邮件专用,用于接收回复的信息,不设置或者设置错误地址,将无法接收回复邮件) |
| ReplyNickName | 回信地址昵称(邮件专用) |
| LinkUrl | pc端链接地址 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_Type | 属性名称 |
| PropertyName\_SenderId | 属性名称 |
| PropertyName\_ReceiverId | 属性名称 |
| PropertyName\_Title | 属性名称 |
| PropertyName\_Content | 属性名称 |
| PropertyName\_LinkContent | 属性名称 |
| PropertyName\_PictureUrl | 属性名称 |
| PropertyName\_SendTime | 属性名称 |
| PropertyName\_State | 属性名称 |
| PropertyName\_AppCode | 属性名称 |
| PropertyName\_SolutionCode | 属性名称 |
| PropertyName\_BatchId | 属性名称 |
| PropertyName\_ReplyAddress | 属性名称 |
| PropertyName\_ReplyNickName | 属性名称 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Notification.UserMessageType,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "type" | 用户消息的类型 |
| "sender" | 发送方 |
| "receiverId" | 接收方 |
| "receiverAddress" | 接收方地址，如果接收方不是系统内部的用户，在这里输入接收方地址 |
| "title" | 用户消息的标题 |
| "content" | 用户消息的内容 |
| "linkContent" | 链接的内容 |
| "appCode" | 应用编码 |
| "batchId" | 批次Id，用于一次性发送同一个批次的消息 |
| "linkUrl" | 链接Url |
| "solutionCode" | 解决方案编码 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "senderId" | 发送者的UserId |
| "receiverAddress" | 接收者号码，多个时使用半角分号隔开 |
| "signature" | 企业签名，一般为企业名称，会附加在短信开头 |
| "title" | 短信内容 |
| 返回值 |  |
| |  |


方法名称 : EntryValidate

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetEntryLinkUrl(System.String,System.String,H3.Entry.EntryType)

| 参数 | 说明 |
| --- | --- |
| "corpId" | 企业corpId |
| "messageHost" | 消息地址 |
| "type" | 接入类型 |
| 返回值 |  |