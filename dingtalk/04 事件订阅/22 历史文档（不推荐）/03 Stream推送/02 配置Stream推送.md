---
title: "配置Stream推送"
source: "https://open.dingtalk.com/document/development/stream"
category: "事件订阅 / 历史文档（不推荐） / Stream推送"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-stream_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-stream_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-16

Stream 模式是钉钉开放平台推荐使用的事件订阅方式，使用 Stream 模式开发者无需提供公网回调地址和注册加解密秘钥，使用 SDK 接入[服务端Stream模式](/document/resourcedownload/introduction-to-stream-mode)，开发者应用程序即可接收到事件内容推送。

## 准备工作

1. 所在钉钉组织[入驻产品方案商](https://open.dingtalk.com/document/isvapp/become-an-application-service-provider)。
2. 拥有所在钉钉组织的[开发者权限](https://open.dingtalk.com/document/isvapp/become-a-dingtalk-developer)。
3. 拥有所在钉钉组织的[第三方企业应用](https://open.dingtalk.com/document/isvapp/create-isvapp)。
4. 拥有访问公网的运行环境。

## **订阅流程**

### **1. 选择Stream模式推送。**

![[development-stream_p672737.png]]

### **2. 服务端接入**

#### **Java接入方式**

1. 添加依赖项到工程的pom.xml文件，SDK最新版本可以在[这里](https://s01.oss.sonatype.org/?spm=openapi-amp.sdkpublish.0.0.78cefAyIfAyImO#nexus-search;gav~com.dingtalk.open~dingtalk-stream~~~)查看和下载。

   ```
     com.dingtalk.open
     dingtalk-stream
     {sdk-version}
   ```
2. 代码示例

   ```java
   public static void main(String[] args) {
     OpenDingTalkStreamClientBuilder
       .custom()
       .credential(new AuthClientCredential("${clientId}", "${clientSecret}"))
       //注册事件监听
       .registerAllEventListener(new GenericEventListener() {
         public EventAckStatus onEvent(GenericOpenDingTalkEvent event) {
           try {
             //事件的唯一Id
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

   参数说明：

   |  |  | | --- | --- | | **参数名** | **说明** | | clientId | 企业内部应用 AppKey/第三方企业应用 SuiteKey。 | | clientSecret | 企业内部应用 AppSecret/第三方企业应用 SuiteSecret。 |

#### **Golang接入方式**

1. 安装 SDK

   ```
   go get github.com/open-dingtalk/dingtalk-stream-sdk-go@v0.1.0
   ```
2. 代码示例

   ```go
   func main() {
       e := clientV2.
           NewBuilder().
           Credential(&clientV2.AuthClientCredential{ClientId: "${clientId}", ClientSecret: "${clientSecret}"}).
           //监听开放平台事件
           RegisterAllEventHandler(func(event *clientV2.GenericOpenDingTalkEvent) clientV2.EventStatus {
               println("receive event ", event.Data)
               //成功返回 clientV2.EventStatusSuccess,失败返回clientV2.EventStatusLater
               return clientV2.EventStatusSuccess
           }).
           Build().
           Start(context.Background())

       if e != nil {
           println("failed to start stream client", e.Error())
           return
       }

       select {}
   }
   ```

### **3. 验证 Stream 模式通道**

客户端启动之后，点击验证 Stream 模式通道按钮完成在线状态验证。

![[development-stream_p672741.png]]

### **4. 保存配置**

完成通道验证之后，点击保存完成并触发**Ticket**推送。

![[development-stream_p672743.png]]

## **数据说明**

Stream 模式推送数据分为两个部分，一个部分为事件的基础信息，另一个部分为事件业务数据信息。以suiteTicket推送事件为例：

**说明**

Stream模式推送格式是以**小驼峰**的命名方式对数据进行推送的。

```json
{
    "eventBornTime":1684132707000,  //事件生成时间
    "eventCorpId":"ding9f50b15b*****41", //事件所属的corpId
    "eventId":"c69632e6e3794bfbb07d33fad9fa82d2", //事件的唯一Id
    "eventType":"suite_ticket", //事件类型
    "eventUnifiedAppId":"unifiedAppId1", //统一应用身份Id
    "data":{ //事件的业务信息
        "suiteTicket":"1234455" //suiteTicke业务信息
    }
}
```