---
title: "iOS分享SDK接入流程"
source: "https://open.dingtalk.com/document/dingstart/mini-app-access"
category: "新手指南 / 移动客户端接入 / 接入钉钉分享"
updated: 
tags:
  - dingtalk
  - 新手指南
---
![[dingstart-mini-app-access_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[dingstart-mini-app-access_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-03本文介绍如何使用钉钉iOS分享SDK接入钉钉分享。

## 准备工作

在使用iOS接入钉钉分享之前，你需要完成以下准备工作：

1. 搭建iOS开发环境。
2. [下载SDK](https://files.alicdn.com/tpsservice/94a5e78286e0d71c935165a28da1514b.zip)（版本号：3.1.0）。

   **说明**
   * iOS DTShareSDK部署系统版本为 iOS 12.0 及以上。
   * 下载并使用本SDK，即表示您已阅读并同意《[钉钉开放平台隐私权政策](/document/services/open-latform-privacy-policy)》、《[钉钉开放平台开发者服务协议](/document/services/open-platform-developer-service-agreement)》。
3. 安装钉钉客户端2.7.0及以上版本。

## 步骤一：**接入钉钉分享**

1. 登录[开发者后台](https://open-dev.dingtalk.com/#/shareMan)，打开应用列表页，单击应用进入应用详情页。

   ![[dingstart-mini-app-access_p386713.png]]
2. 在应用信息页面，获取应用的AppKey。

   ![[dingstart-mini-app-access_p386725.png]]
3. 在应用详情页，单击**钉钉登录与分享**，进入登录与分享页面。

   ![[dingstart-mini-app-access_p386717.png]]
4. 在**接入分享**栏，单击右侧**编辑**。

   ![[dingstart-mini-app-access_p386718.png]]
5. 单击开启**iOS 分享**，然后输入**iOS Bundle ID**，最后单击保存。

   **说明**

   iOS Bundle ID应填写你的iOS应用对应的ID。

   ![[dingstart-mini-app-access_p255022.png]]

## 步骤二：配置iOS应用

1. 将已下载的iOS SDK的framework导入到工程中。

   ![[dingstart-mini-app-access_p163310.png]]
2. 配置工程。

   1. 在**Other Linker Flags**添加 `-all_load`选项。

      ![[dingstart-mini-app-access_p163311.png]]
   2. 在**Custom iOS Target Properties**的**LSApplicationQueriesSchemes**列表中添加dingtalk、dingtalk-open。

      **说明**

      iOS系统限制LSApplicationQueriesSchemes最多只能有50个，超出部分有可能不生效。尤其是Xcode13打包，iOS15.0及以上，超出部分不生效。
   3. 在**URL Types**中配置以下信息。

      |  |  | | --- | --- | | 内容 | 配置说明 | | **Identifier** | dingtalk | | **URL Schemes** | 填写步骤一中获取的AppKey。 ![[dingstart-mini-app-access_p386725.png]] |

      ![[dingstart-mini-app-access_p386729.png]]

   **说明**

   iOS9及以后的系统需要将钉钉和分享SDK的scheme配置在Info.plist。

## 步骤三：**在代码中使用开发工具包**

1. 注册应用并添加必要的URLHandler。

   **说明**

   代码中的 `[DTOpenAPl registerApp:@"appld"]` 中的 appId 为应用的 [Client ID](/document/dingstart/basic-concepts-beta#section-pje-9wf-l7c)（原应用 AppKey）。

   如示例中，在AppDelegate.m文件中引用`AppDelegate.h`，在@implementation AppDelegate中增加如下代码：

   ![[dingstart-mini-app-access_p163313.png]]
2. 分享数据到钉钉客户端。

   发送分享请求的过程主要分为两部分：

   1. 组装DTMediaMessage对象。

      不同类型的分享数据通过DTMediaMessage的mediaObject区分。

      |  |  | | --- | --- | | **类型** | **描述** | | DTMediaTextObject | 纯文本数据。 | | DTMediaImageObject | 纯图片数据。 | | DTMediaWebObject | Web页面数据。 |
   2. 调用`+[DTOpenAPI sendReq:]`发送数据。

   下面是分享文本部分代码，其他类型请参考 SDK 相关方法注释：

   ```
   DTSendMessageToDingTalkReq *sendMessageReq = [[DTSendMessageToDingTalkReq alloc] init];

   DTMediaMessage *mediaMessage = [[DTMediaMessage alloc] init];

   DTMediaTextObject *textObject = [[DTMediaTextObject alloc] init];
   textObject.text = @"Hi DingTalk.";

   mediaMessage.mediaObject = textObject;
   sendMessageReq.message = mediaMessage;
   [DTOpenAPI sendReq:sendMessageReq completion:^(BOOL success) {
     if (success) {
          NSLog(@"[DTShareKitDemo] Text 发送成功.");
        }
     else {
          NSLog(@"[DTShareKitDemo] Text 发送失败.");
        }
    }];
   ```

   **说明**
   * 分享纯图片数据和Web页面缩略图时，可以使用图片URL和图片Data两种形式，钉钉内优先使用图片Data形式。
   * 分享数据的数据量限制在SDK的头文件中均有描述，超过限制的数据不会发送到钉钉客户端。
3. 判断当前设备是否支持分享到钉钉。

   钉钉从2.7版本开始支持分享，SDK中提供了接口来判断当前设备是否能够支持分享到钉钉。

   ```
   /**
    检测设备是否安装了钉钉客户端.

    @return YES 设备安装了钉钉客户端. NO 设备没有安装钉钉客户端.
    */
   + (BOOL)isDingTalkInstalled;

   /**
    检测设备安装的钉钉是否支持钉钉OpenAPI.

    @return YES 设备安装的钉钉客户端支持钉钉OpenAPI. NO 设备安装的钉钉客户端不支持钉钉OpenAPI.
    */
   + (BOOL)isDingTalkSupportOpenAPI;

   /**
    检测设备安装的钉钉是否支持钉钉SSO授权.

    @return YES 设备安装的钉钉客户端支持钉钉SSO授权. NO 设备安装的钉钉客户端不支持钉钉SSO授权.
    */
   + (BOOL)isDingTalkSupportSSO;
   ```

   **说明**

   在iOS9上需要将钉钉SDK相关的Scheme注册到Info.plist的LSApplicationQueriesSchemes名单中，否则会导致检测方法总是返回NO。