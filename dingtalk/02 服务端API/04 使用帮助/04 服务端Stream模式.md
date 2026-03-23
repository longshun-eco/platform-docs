---
title: "服务端Stream模式"
source: "https://open.dingtalk.com/document/development/introduction-to-stream-mode"
category: "服务端API / 使用帮助"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-introduction-to-stream-mode_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-introduction-to-stream-mode_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-08本文介绍钉钉开放平台Stream模式的基本能力、设计原理及服务端接入方式，帮助开发者快速实现与钉钉的实时通信。

## 适用对象

本接入方式适用于以下应用类型：

* ✅ 企业内部应用
* ✅ 第三方企业应用

## **什么是Stream模式**

Stream 模式是钉钉开放平台提供的一种集成方式，它可以监听机器人回调、事件订阅回调和注册卡片回调。使用 Stream 模式接入，钉钉开放平台将通过 Websocket 连接与应用程序通讯，Stream 模式将极大降低接入门槛和资源依赖，不需要公网服务器、IP、域名等资源，只需集成钉钉开放平台 SDK 即可。

## Stream模式原理

在 Stream 模式下，开发者的应用程序通过集成官方 SDK 与钉钉开放平台建立一条持久化的 WebSocket 连接。连接过程中，平台会对客户端进行身份鉴权，确保通信安全性。

当用户触发机器人消息、事件变更或卡片交互时，钉钉开放平台会通过已建立的 WebSocket 连接，将回调数据实时推送给客户端。应用程序可即时处理这些数据并返回响应，从而实现低延迟、高可用的双向通信。

![[development-introduction-to-stream-mode_p645637.png]]

## **Stream模式优势**

在钉钉开放平台向应用程序发送请求的场景中，大部分都是采用 Webhook （注册公网 HTTPS 服务）的方式，包括卡片回调，使用 Webhook 方式开发过程中会遇到较多的问题，包括

* 申请公网域名和TLS证书
* 申请公网IP并部署接入网关
* 部署应用防火墙并配置白名单
* 独立处理请求的鉴权，以及加解密处理
* 搭建内网穿透环境进行本地开发调试

针对以上问题，Stream 模式将为开发者提供"五零"接入体验，将1~2周的接入开发周期降低到5分钟，包括

* **零公网IP**

  不需要依赖公网IP或域名，也不需要暴露公网IP，减少了公网暴露服务的安全风险并降低了开发门槛。
* **零加解密/签名/TLS证书管理**

  使用应用身份对连接进行鉴权，通过反向连接的方式与钉钉开放平台建立TLS加密连接，提供了快速、安全的通信体验。
* **零防火墙白名单**

  Stream 模式下开发者无需向公网开放提供任何服务端口，无需部署防火墙和配置白名单。
* **零网关部署**

  通过反向连接的方式建立通道，开发者只需保证运行环境具备公网访问能力即可，无需部署网关。
* **零内网穿透**

  开发者无需在本地搭建内网穿透工具，通过 Stream 模式在本地开发环境中即可接收卡片回调。

## **接入方式**

**重要**

客户端启动后即可收到对应卡片的回调，测试、开发环境部署要避免影响生产环境。

### **接入限制**

1. 应用所部署的运行环境必须具备访问公网的能力；
2. 仅适用于企业内部开发和第三方企业应用。
3. 每个客户端实例默认建立一条 WebSocket 连接，单个应用最多支持 50 条并发连接。

### **前置准备**

* 创建一个**企业内部应用**或**第三方企业应用**；
* 获取应用凭证：

  + **Client ID**：即 AppKey（企业内部应用）或 SuiteKey（第三方应用），位于【应用详情 → 基本信息】中；
  + **Client Secret**：对应 AppSecret 或 SuiteSecret，同一位置查看。

### **Java**

* #### **运行环境**

  JDK1.8及以上。
* #### **安装Java SDK**

  添加依赖项到工程的`pom.xml`文件或下载对应的jar包，最新的 SDK 版本可以在[这里](https://s01.oss.sonatype.org/?spm=ding_open_doc.document.0.0.27fc4169or3Sre#nexus-search;quick~dingtalk-stream)查看和下载。

  ```
    com.dingtalk.open
    dingtalk-stream
    {sdk-version}
  ```
* #### **示例代码**

  **机器人回调**

  ```java
  public static void main(String[] args) throws Exception {
          OpenDingTalkStreamClientBuilder
                  .custom()
                  .credential(new AuthClientCredential("${clientId}", "${clientSecret}"))
                  //注册机器人监听器
                  .registerCallbackListener("${topic}", robotMessage -> {
                      log.info("receive robotMessage, {}", robotMessage);
                      //开发者根据自身业务需求，处理机器人回调
                      return new JSONObject();

                  })
                  .build().start();
  }
  ```

  详情参见[机器人开发文档](https://opensource.dingtalk.com/developerpedia/docs/category/%E8%81%8A%E5%A4%A9%E6%9C%BA%E5%99%A8%E4%BA%BA)。

  **参数说明**

  |  |  | | --- | --- | | **参数名** | **说明** | | clientId | 企业内部开发 AppKey/第三方企业应用 SuiteKey。 | | clientSecret | 企业内部开发 AppSecret/第三方企业应用 SuiteSecret。 | | topic | 机器人回调名称，固定值：`/v1.0/im/bot/messages/get`。 |

  **事件订阅回调**

  ```java
  public static void main(String[] args) {
    OpenDingTalkStreamClientBuilder
      .custom()
      .credential(new AuthClientCredential("${clientId}", "${clientSecret}"))
      //注册事件监听
      .registerAllEventListener(new GenericEventListener() {
        public EventAckStatus onEvent(GenericOpenDingTalkEvent event) {
          try {
            //事件唯一Id
            String eventId = event.getEventId();
            //事件类型
            String eventType = event.getEventType();
            //事件产生时间
            Long bornTime = event.getEventBornTime();
            //获取事件体
            JSONObject bizData = event.getData();
            //处理事件
            process(bizData);
            //消费成功
            return EventAckStatus.SUCCESS;
          } catch (Exception e) {
  ```

  详情参见[配置 Stream 推送（推荐）](/document/development/configure-stream-push#151be9e66238j)。

  **参数说明**

  |  |  | | --- | --- | | **参数名** | **说明** | | clientId | 企业内部开发 AppKey/第三方企业应用 SuiteKey。 | | clientSecret | 企业内部开发 AppSecret/第三方企业应用 SuiteSecret。 |

  **卡片回调**

  ```java
  public static void main(String[] args) throws Exception {
          OpenDingTalkStreamClientBuilder
                  .custom()
                  .credential(new AuthClientCredential("${clientId}", "${clientSecret}"))
                  //注册卡片回传监听器
                  .registerCallbackListener("/v1.0/card/instances/callback", callbackData -> {
                      log.info("receive call back request, {}", callbackData);
                      //your code is here

                      //开发者根据自身业务需求，变更卡片内容，返回response
                      CardCallbackResponse resp = new CardCallbackResponse();
                      return resp;

                  })
                  .build().start();
  }
  ```

  详情参见[互动卡片 Stream](/document/orgapp/event-callback-card#a0cb7b50dfnlu) 。

  **参数说明**

  |  |  | | --- | --- | | **参数名** | **说明** | | clientId | 企业内部开发 AppKey/第三方企业应用 SuiteKey。 | | clientSecret | 企业内部开发 AppSecret/第三方企业应用 SuiteSecret。 | | topic | 注册的卡片回调名称，固定值：`/v1.0/card/instances/callback`。 |

### **Golang**

* #### **运行环境**

  1.16及以上。
* #### **安装SDK**

  ```
  go get github.com/open-dingtalk/dingtalk-stream-sdk-go
  ```
* #### **示例代码**

  **机器人回调**

  ```go
  func OnChatReceive(ctx context.Context, data *chatbot.BotCallbackDataModel) error {
      return nil
  }

  func StartRobot() {
      logger.SetLogger(logger.NewStdTestLogger())
      cli := client.NewStreamClient(
      client.WithAppCredential(client.NewAppCredentialConfig(${clientId}, ${clientSecret})),
          client.WithUserAgent(client.NewDingtalkGoSDKUserAgent()),
      client.WithSubscription(utils.SubscriptionTypeKCallback, ${topic}, chatbot.NewDefaultChatBotFrameHandler(OnChatReceive).OnEventReceived),
      )

      err := cli.Start(context.Background())
      if err != nil {
          panic(err)
      }

      defer cli.Close()

      select {}
  }
  ```

  **参数说明**

  |  |  | | --- | --- | | **参数名** | **说明** | | clientId | 企业内部开发 AppKey/第三方企业应用 SuiteKey。 | | clientSecret | 企业内部开发 AppSecret/第三方企业应用 SuiteSecret。 | | topic | 机器人回调名称，固定值：`/v1.0/im/bot/messages/get`。 |

### **其他语言接入方式**

* [Java SDK接入示例工程](https://github.com/open-dingtalk/dingtalk-stream-sdk-java-quick-start)
* [Golang SDK及示例代码](https://github.com/open-dingtalk/dingtalk-stream-sdk-go)
* [Python SDK及示例代码](https://github.com/open-dingtalk/dingtalk-stream-sdk-python)
* [Node.js SDK及示例代码](https://github.com/open-dingtalk/dingtalk-stream-sdk-nodejs)

过程中有问题也可以通过[技术支持](https://open-dingtalk.github.io/developerpedia/docs/explore/support)提交反馈和问题交流。

## **技术支持**

开发过程中如有任何疑问，可加入钉钉 Stream 模式共创群咨询答疑，[Stream 模式共创群](https://open-dingtalk.github.io/developerpedia/docs/explore/support?via=moon-group)。