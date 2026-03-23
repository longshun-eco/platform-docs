---
title: "鸿蒙分享SDK接入流程"
source: "https://open.dingtalk.com/document/dingstart/harmony-share-the-sdk-access-process"
category: "新手指南 / 移动客户端接入 / 接入钉钉分享"
updated: 
tags:
  - dingtalk
  - 新手指南
---
![[dingstart-harmony-share-the-sdk-access-process_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[dingstart-harmony-share-the-sdk-access-process_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-08本文介绍如何使用钉钉鸿蒙分享SDK接入钉钉分享。

## 准备工作

在使用鸿蒙接入钉钉分享之前，你需要完成以下准备工作：

* 搭建 鸿蒙 开发环境（建议IDE 5.0.3.906以上，API12及以上）。
* 下载鸿蒙分享SDK Har包。

  [ddsharesdk.har](https://help-static-aliyun-doc.aliyuncs.com/file-manage-files/zh-CN/20251031/zqfluo/ddsharesdk.har)
* 安装钉钉客户端 7.6.23 及以上的版本。

**说明**

下载并使用本SDK，即表示您已阅读并同意《[钉钉开放平台隐私权政策](/document/services/open-latform-privacy-policy)》、《[钉钉开放平台开发者服务协议](/document/services/open-platform-developer-service-agreement)》。

## 步骤一：接入钉钉分享

1. 登录[开发者后台](https://open-dev.dingtalk.com/#/shareMan)，创建应用

   ![[dingstart-harmony-share-the-sdk-access-process_p878408.png]]
2. 找到自己的创建的应用，单击应用进入应用详情页。

   ![[dingstart-harmony-share-the-sdk-access-process_p878409.png]]
3. 在应用信息页面，获取应用的 **Client ID**。

   ![[dingstart-harmony-share-the-sdk-access-process_p878410.png]]
4. 在应用详情页，单击**分享设置**，进入登录与分享页面。

   ![[dingstart-harmony-share-the-sdk-access-process_p878411.png]]
5. 在**接入分享**栏，单击右侧**编辑**。

   ![[dingstart-harmony-share-the-sdk-access-process_p878412.png]]
6. 单击开启 鸿蒙 **分享**，然后依次填写鸿蒙应用 **Bundle Name**和 **Identifier**，最后单击保存。

   ![[dingstart-harmony-share-the-sdk-access-process_p878414.png]]

   注意：**Identifier** 为 鸿蒙应用唯一标识 **appIdentifier** 而不是 appId，详情见官方文档：[BundleInfo](https://developer.huawei.com/consumer/cn/doc/harmonyos-references-V14/js-apis-bundlemanager-bundleinfo-V14)

## 步骤二：搭建开发环境

使用以下任意一种方式搭建开发环境。

方式一：使用demo中的har包直接安装

参考：<https://developer.huawei.com/consumer/cn/doc/harmonyos-guides-V5/ide-ohpm-install-V5>。

方式二：通过三方库引入

上架三方工具库，通过ohpm -i安装。目前鸿蒙SDK暂未上架三方工具库，敬请期待。

## 步骤三：在代码中使用开发工具包

如果您的程序需要接收钉钉发送的请求，或者接收发送到钉钉的请求的响应结果，需要执行以下操作：

1. 获取分享API

```javascript
import { BaseResp, IDDAPIEventHandler, BaseReq, SendMessageToDD, ErrCode, DDShareApi } from "@dingtalk/ddsharesdk"
import { promptAction } from '@kit.ArkUI';

export class DDApiEventHandlerImpl implements IDDAPIEventHandler {

  onReq(req: BaseReq): void {
    console.log("DDTag 来自钉钉的请求");
  }

  onResp(resp: BaseResp): void {
    let errCode = resp.mErrCode;
    if (resp instanceof SendMessageToDD.Resp) {
      switch (errCode) {
        case ErrCode.ERR_OK:
          promptAction.showToast({
            message: "分享成功",
            duration: 2000
          })
        break;
        case ErrCode.ERR_USER_CANCEL:
          promptAction.showToast({
```

// 在EntryAbility 或应用自身的Ability 中响应来自钉钉的回调：

```javascript
export default class EntryAbility extends UIAbility {
  onCreate(want: Want, launchParam: AbilityConstant.LaunchParam): void {
    this.handleDingTalkCallIfNeed(want);
  }

  onNewWant(want: Want, launchParam: AbilityConstant.LaunchParam): void {
    this.handleDingTalkCallIfNeed(want);
  }

  private  handleDingTalkCallIfNeed(want: Want) {
    DDApi.handleWant(want, DDEventHandle);
  }
}
```

2. 支持图片/文字/链接 等，具体使用请参考已下载的**Harmony dingtalk\_share\_demo**示例：

   [dingtalk\_share\_demo.zip](https://help-static-aliyun-doc.aliyuncs.com/file-manage-files/zh-CN/20251031/grvroo/dingtalk_share_demo.zip)

## 鸿蒙应用开发手册

* 在代码中接入SDK后，可调用接口实现钉钉分享功能
* 当前支持图片/文字/链接等分享到钉钉会话

### DDMediaMessage（钉钉媒体消息）

|  |  |  |  |
| --- | --- | --- | --- |
| 字段 | 类型 | 含义 | 备注 |
| mMediaMessageObject | IMediaObject | 消息对象 | 描述媒体对象 |
| mTitle | string | 消息标题 |  |
| mThumbData | Uint8Array | 缩略图数据 | // 暂不支持解析 |
| mThumbUrl | string | 缩略图链接 |  |
| mUrl | string | 消息链接 |  |
| mContent | string | 消息内容 |  |

### SendMessageToDD.Req（发送请求）

|  |  |  |  |
| --- | --- | --- | --- |
| 字段 | 类型 | 含义 | 备注 |
| mMediaMessage | DDMediaMessage | 媒体对象 |  |
| mScene | number | 场景 |  |

### **示例**

一、文本分享类型

|  |  |  |  |
| --- | --- | --- | --- |
| 字段 | 类型 | 含义 | 备注 |
| mText | string | 文本数据 | 不允许超过6k |

文本类型分享demo

```java
  let req: SendMessageToDD.Req | undefined = undefined;

  if (this.shareText) {
  let text: string = this.textContent;
  /** 构造text消息*/
  let textMessage: DDTextMessage = new DDTextMessage();
  textMessage.mText = text;

  let mediaMessage = new DDMediaMessage();
  mediaMessage.mMediaMessageObject = textMessage;

  req = new SendMessageToDD.Req();
  req.mMediaMessage = mediaMessage;

   // 返回需要打开的 Ability，不传的时候默认为 EntryAbility
   if (req) {
     req.callbackAbility = "";
   }
  if(this.mDDShareAPI != null) {
    this.mDDShareAPI.sendReq(req);
  }
```

二、图片类型分享示例

|  |  |  |  |
| --- | --- | --- | --- |
| 字段 | 类型 | 含义 | 备注 |
| mImageUri | string | 本地图片链接Uri |  |

图片类型分享demo

```java
    let req: SendMessageToDD.Req | undefined = undefined;
    /**
     * 构造Image消息
     * 注意：目前仅支持Uri
     */
    let imageMessage = new DDImageMessage();
    imageMessage.mImageUri = fileUri.getUriFromPath(Utils.getImageCacheFile(getContext()) + "/aaa.png");

    let mediaMessage = new DDMediaMessage();
    mediaMessage.mMediaMessageObject = imageMessage;

    req = new SendMessageToDD.Req();
    req.mMediaMessage = mediaMessage;

    // 返回需要打开的 Ability，不传的时候默认为 EntryAbility
    if (req) {
      req.callbackAbility = "";
    }
    if(this.mDDShareAPI != null) {
      this.mDDShareAPI.sendReq(req);
    }
```

三、链接类型分享示例

|  |  |  |  |
| --- | --- | --- | --- |
| 字段 | 类型 | 含义 | 备注 |
| mUrl | string | web链接 |  |

Web链接类型分享demo

```java
    let req: SendMessageToDD.Req | undefined = undefined;
    let webpMessageObject = new DDWebPageMessage();
    webpMessageObject.mUrl = "http://www.baidu.com";

    let webpMessage = new DDMediaMessage();
    webpMessage.mMediaMessageObject = webpMessageObject;
    webpMessage.mTitle = "TestTitle";
    webpMessage.mThumbUrl = "http://static.dingtalk.com/media/lAHPBY0V4shLSVDMlszw_240_150.gif";

    req = new SendMessageToDD.Req();
    req.mMediaMessage = webpMessage;

    // 返回需要打开的 Ability，不传的时候默认为 EntryAbility
    if (req) {
      req.callbackAbility = "";
    }
    if(this.mDDShareAPI != null) {
      this.mDDShareAPI.sendReq(req);
    }
```

支持拉起专属钉：

```
// 需要拉起目标的bundleName，默认为标准钉
req.targetAppBundleName = "**";
```

## 常见问题-FAQ

1. **我登录开发者后台提示「暂无权限访问」，该怎么处理？**

需要有应用开发相应的权限才能登录使用，可以参考这个文档了解如何[获取开发者权限](/document/dingstart/get-developer-permissions)。