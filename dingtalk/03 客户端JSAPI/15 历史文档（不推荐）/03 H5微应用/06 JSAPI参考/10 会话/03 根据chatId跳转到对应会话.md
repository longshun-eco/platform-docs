---
title: "根据chatId跳转到对应会话"
source: "https://open.dingtalk.com/document/development/redirects-to-a-specific-session-based-on-the-chatid-h5"
category: "客户端JSAPI / 历史文档（不推荐） / H5微应用 / JSAPI参考 / 会话"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-redirects-to-a-specific-session-based-on-the-chatid-h5_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-redirects-to-a-specific-session-based-on-the-chatid-h5_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**biz.chat.toConversation**根据chatId跳转到对应会话。

## 调试

访问[JSAPI Explorer](https://open-dev.dingtalk.com/apiExplorer#/jsapi?api=biz.chat.toConversation)在线调试该接口。

## 使用说明

调用本接口前，请先引入钉钉js，参考[准备工作](/document/orgapp/read-before-development)。

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **客户端** | **是否需要鉴权** | **Android** | **iOS** | **PC** |
| 支持说明 | 需要 | 支持 | 支持 | 不支持 |

```javascript
dd.biz.chat.toConversation({
    corpId: 'xxx', ////企业corpId,必须是用户所属的企业的corpId
    chatId:'xxx',//会话chatId
    onSuccess : function() {},
    onFail : function() {}
})
```

## 参数说明

|  |  |  |
| --- | --- | --- |
| 参数 | 类型 | 说明 |
| corpId | String | 企业的corpid，可在[开发者后台](https://open-dev.dingtalk.com/)首页查看。 |
| chatId | String | 会话id。可调用[根据corpid选择会话](/document/orgapp/select-session-based-on-corpid)获取。 |