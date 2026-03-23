---
title: "根据corpid选择会话"
source: "https://open.dingtalk.com/document/development/select-session-based-on-corpid"
category: "客户端JSAPI / 历史文档（不推荐） / H5微应用 / JSAPI参考 / 会话"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-select-session-based-on-corpid_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-select-session-based-on-corpid_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**biz.chat.chooseConversationByCorpId**根据corpid选择会话。

## 调试

访问[JSAPI Explorer](https://open-dev.dingtalk.com/apiExplorer#/jsapi?api=biz.chat.chooseConversationByCorpId)在线调试该接口。

## 使用说明

|  |  |  |  |
| --- | --- | --- | --- |
| **客户端** | **Android** | **iOS** | **PC** |
| 支持说明 | 支持 | 支持 | 支持 |

```javascript
dd.biz.chat.chooseConversationByCorpId({
    corpId: 'xxx', //企业id,必须是用户所属的企业的corpid
    isAllowCreateGroup:false,
    filterNotOwnerGroup:false,
    onSuccess : function() {
        /*{
            chatId: 'xxxx',
            title:'xxx'
        }*/
},
    onFail : function() {}
})
```

## 参数说明

|  |  |  |
| --- | --- | --- |
| 参数 | 类型 | 说明 |
| corpId | String | 企业的corpid，可在[开发者后台](https://open-dev.dingtalk.com/)首页查看。 |
| isAllowCreateGroup | Boolean | 是否允许创建会话：   * **true**：允许 * **false**：不允许 |
| filterNotOwnerGroup | Boolean | 是否限制为自己创建的会话。 |

## 返回结果

|  |  |
| --- | --- |
| 参数 | 说明 |
| chatId | 会话id。  **重要**  后续版本中chatid将不再使用，请将openConversationId作为群会话唯一标识。 |
| openConversationId | 会话id。 |
| title | 会话标题。 |