---
title: "企业内部机器人使用Webhook发送群聊消息"
source: "https://open.dingtalk.com/document/development/assign-a-webhook-url-to-an-internal-chatbot"
category: "服务端API / 历史文档（不推荐） / 即时通信IM / 机器人 / 使用教程"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-assign-a-webhook-url-to-an-internal-chatbot_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-assign-a-webhook-url-to-an-internal-chatbot_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-14本文介绍了如何获取企业内部机器人的Webhook来发送消息。

## 流程简介

步骤一：登录[开发者后台](https://open-dev.dingtalk.com/#/)，创建[机器人](https://open.dingtalk.com/document/orgapp/enterprise-created-chatbot)。

步骤二：获取AppKey和AppSecret。

步骤三：发布机器人应用。

步骤四：客户端创建企业内部群会话。

步骤五：群会话添加企业内部机器人。

步骤六：获取企业内部机器人Webhook。

步骤七：通过Webhook发送消息。

**说明**

本流程使用机器人Webhook的方式发送群聊消息，推荐使用服务端API-[机器人发送群聊消息](https://open.dingtalk.com/document/orgapp/the-robot-sends-a-group-message)接口，实现发送群消息。

## 步骤一：创建企业内部开发-机器人 ![[development-assign-a-webhook-url-to-an-internal-chatbot_p385216.png]]

## 步骤二：获取AppKey和AppSecret

获取AppKey和AppSecret。

![[development-assign-a-webhook-url-to-an-internal-chatbot_p385218.png]]

## 步骤三：发布机器人应用

进入版本管理与发布页面，点击上线，机器人的状态变更为已发布。

![[development-assign-a-webhook-url-to-an-internal-chatbot_p385221.png]]

## 步骤四：客户端创建企业内部群会话

在机器人所在的企业，创建一个企业内部群。如已有该企业的企业内部群，此步骤可跳过。

![[development-assign-a-webhook-url-to-an-internal-chatbot_p384754.png]]

## 步骤五：添加企业内部机器人

添加机器人到企业内部群。

![[development-assign-a-webhook-url-to-an-internal-chatbot_p385227.png]]

## 步骤六：获取机器人Webhook

![[development-assign-a-webhook-url-to-an-internal-chatbot_p411080.png]]

## 步骤七：通过Webhook发送消息

**说明**

发送Webhook消息前需安装SDK。请参考[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。

![[development-assign-a-webhook-url-to-an-internal-chatbot_p411083.png]]

使用Webhook发送消息的类型和格式请参考[消息类型](https://open.dingtalk.com/document/orgapp/robot-message-types-and-data-format)。

```java
public void sendMessageWebhook() throws ApiException {
        DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/robot/send?access_token=xxxxxxxxxxxx");
        OapiRobotSendRequest request = new OapiRobotSendRequest();
        request.setMsgtype("text");
        OapiRobotSendRequest.Text text = new OapiRobotSendRequest.Text();
        text.setContent("测试文本消息");
        request.setText(text);
        OapiRobotSendRequest.At at = new OapiRobotSendRequest.At();
        at.setAtUserIds(Arrays.asList("4525xxxxxxxxx7041"));
        at.setIsAtAll(false);
        request.setAt(at);
        OapiRobotSendResponse response = client.execute(request);
        System.out.println(response.getBody());
}
```