---
title: "如何获取 traceid"
source: "https://docs.aliwork.com/docs/yida_support/lbtl0t/ocmxyv/nztfe0"
category: "用戶手冊 / 开发者功能（需有代码基础） / JS 动作面板 - 前端代码开发"
updated: 
tags:
  - yida
  - 用戶手冊
---
**eagleeye-traceid** 是一次请求的唯一标识，开发同学使用其进行用户进行问题排查使用的。

**操作步骤**
**1\. 打开开发者工具**
快捷键：f12，若无效，可按下图流程：
1点击右上角的三个点
2点击更多工具
3点击开发者工具
4点击network

![[yida_support-lbtl0t-ocmxyv-nztfe0_1661839663710-6443d9bf-b6bf-464c-802b-5fd4c7526e39.png]]



![[yida_support-lbtl0t-ocmxyv-nztfe0_1661839682331-2b8430eb-fc70-4452-b068-60d197438375.png]]

![[yida_support-lbtl0t-ocmxyv-nztfe0_1661839702692-9901a2c4-2bf8-4f08-bda0-ce98bd1aeb21.png]]


**2\. 搜索特定请求**

注：具体搜索内容请联系开发获取


![[yida_support-lbtl0t-ocmxyv-nztfe0_1661839723573-affb68dd-eaf0-4bc5-b1cd-f6a6cff1f3ad.png]]



**3\. 获取 traceId**

请求->Headers -> Response Headers -> eagleeye-traceid 即为 traceId ，拷贝该值给开发同学即可


![[yida_support-lbtl0t-ocmxyv-nztfe0_1661839745146-83cfefac-a3c1-4a75-bd0f-928c87f69b28.png]]











若有收获，就点个赞吧