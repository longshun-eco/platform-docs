---
title: "前端JSAPI调试工具"
source: "https://open.dingtalk.com/document/download/jsapi-explorer"
category: "工具与资源 / 开发者工具"
updated: 
tags:
  - dingtalk
  - 工具与资源
---
![[download-jsapi-explorer_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[download-jsapi-explorer_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-13JSAPI Explorer是钉钉开放平台提供的可视化微应用JSAPI调用工具，方便开发者在线发起JSAPI调用。本文将以JSAPI Explorer工具调用发起DING消息JSAPI给某人发送DING消息为例，帮助您快速了解JSAPI Explorer工具的使用。

## 步骤一：连接控制台

参考以下操作，使用JSAPI Explorer工具连接手机控制台。

1. 打开[JSAPI Explorer](https://open.dingtalk.com/tools/explorer/jsapi)工具，通过搜索“createDing”快速定位JSAPI。本示例以**发起DING****消息**JSAPI为例，给某人发送DING消息为例。

   ![[download-jsapi-explorer_p1025952.png]]
2. 选择需要预览的类型，使用钉钉移动端扫描右侧二维码，连接控制台。

   **说明**

   平台提供了**微应用移动端**和**小程序移动端**调试功能，但部分接口仅支持其中一种，可根据实际情况选择对应类型进行连接。

   ![[download-jsapi-explorer_p1025953.png]]
3. 根据提示完成手机扫码授权，单击**确定**。

   **说明**

   当控制台连接成功后，在没有断开连接的前提下，调用其他API时可忽略步骤一，断开连接后需重新连接手机控制台。

   ![[download-jsapi-explorer_p1025958.png]]

   若连接成功后，调试台右侧的**运行调试**按钮会变为可点击状态：

   ![[download-jsapi-explorer_p1025961.png]]

## 步骤二：发起调用

参考以下操作，使用**JSAPI Explorer**工具给某人发送DING消息，完成**发起DING****消息**JSAPI调用：

1. 控制台连接成功后，点击右侧示例代码下方的**运行调试**按钮，发起调试。

   **说明**

   Android端和iOS端不同系统展示结果可能会出现差别，请以最终的展示效果为准。

   ![[download-jsapi-explorer_p1025961.png]]
2. 手机端和PC端同时返回调用结果，效果如下图所示。

   手机端效果图：

   ![[download-jsapi-explorer_p1026007.png]]

   PC端效果图：

   ![[download-jsapi-explorer_p1026008.png]]