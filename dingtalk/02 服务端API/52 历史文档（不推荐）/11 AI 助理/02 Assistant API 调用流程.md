---
title: "Assistant API 调用流程"
source: "https://open.dingtalk.com/document/development/assistantapi-call-process"
category: "服务端API / 历史文档（不推荐） / AI 助理"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-assistantapi-call-process_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-assistantapi-call-process_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-03-06本文主要介绍了如何使用 Assistant API 的方式发起跟AI助理的聊天交互。

**重要**

本文档已于 2026年 03 月 05 日迁移至历史文档（不推荐）目录，且本文档及相关接口仅保持现有功能，不再新增支持其他能力。

## **前提条件**

创建好了自定义 AI 助理。创建的方式有以下 2 种：

* 在客户端以下入口进行创建，按照正常引导流程操作即可。

  ![[development-assistantapi-call-process_p830813.png]]
* 助理创建完成后，获取调用 Assistant API 的凭证信息，需要查询到助理关联应用的 Client ID 和 Client Secret 等信息。 操作路径是“进入到助理编辑页”>“选择集成开发”。

  ![[development-assistantapi-call-process_p925578.png]]

## **功能简介**

* 开发者可以使用 Assistant API 给 AI 助理发送消息并发起交互，然后获取AI助理的回答。
* 适用于钉钉端外环境集成钉钉AI助理的能力，比如集成于微信公众号，把 AI 助理的回复作为公众号的响应，让公众号也能拥有钉钉 AI 助理同样的能力；也可以集成到企业内部的系统。

## **概览**

开发者需要完成以下三个步骤

1、创建一个线程（Thread），用于用户开启一段对话。

2、添加一个消息（Message）到线程（Thread）中，作为用户的提问（Query）。

3、运行（Run）Assistant在指定的线程（Thread）上，让Assistant生成回答。

### **步骤一:创建Thread**

Thread是一个用户跟AI助理的对话空间，相关的Message信息都存放在Thread中。

具体信息参考[创建线程](/document/development/api-createassistantthread)文档

### **步骤二:添加Message到Thread中**

* 用户的Query的信息可以通过Message传入，可以创建一个Message给到指定的线程（Thread）；

具体信息参考[创建消息](/document/development/api-createassistantmessage)文档

### **步骤三:创建Run，开始运行**

* 用户可以通过“Run”这个Thread来运行创建好的Assistant。
* AI助理会智能地选择并回答用户的问题最终生成的答案，并将过程中产生的内容以Message的形式添加进Thread中。
* 有2种运行Run的方式（二选一）

  + 非流式
  + 流式

#### **1、非流式Run**

创建非流式Run之后需要以轮询的方式检索Run，检索当前Run实例的状态（status）是否是一个结束状态，是则停止轮询；如果状态是“complete”时，再通过Message的list方法获取AI助理的回复内容列表。

**接入参考文档：**

* [创建AI助理的运行任务](/document/development/api-createassistantrun)文档
* [获取AI助理的运行任务](/document/development/api-retrieveassistantrun)文档
* [获取AI助理的消息列表](/document/development/api-listassistantmessage)文档

**重要**

**注意：**

* 由于可能模型使用人数过多，可能需要花费一定时间等待运行结束，因此建议等待Run的状态为“complete”后再去取消息。

#### **2、流式Run**

创建流式Run之后，AI助理回复的消息就会出现在流式数据中，开发者需要根据不同消息的格式进行解析， 最后再输出到自己的业务系统中。 注意：流式Run无需轮询检索Run状态，也不需要读取Message列表

**接入参考文档：**[创建AI助理的运行任务](/document/development/api-createassistantrun)文档。

**说明**

* 每一次流式推送的数据包含了一组 event 和 data，开发者需要根据 event 的类型，去解析 data 中的JSON数据。
* event 类型中需要特殊说明的是：thread.message.delta，该 event 对应的 data 存放了AI助理的回复内容，开发者拿到data后需要先解析出 messageId 和 mode，根据 messageId 确定当前的流式消息内容归属于哪一条消息，然后再根据 mode 进行处理，存放到业务自己的内存缓存中，说明如下：

  + 如果 mode 是“overwrite”，即是覆盖模式，那缓存中 message 内容就直接更新为当前的流式消息内容；
  + 如果 mode 是“append”，即是增量模式，那就将当前的流式消息内容追加到缓存中；

流式数据格式：

```
event:thread.run.created
data:{"assistantId":"1039246b3f2249b38d9a69da2a2b0681","createAt":1722862859475,"expiredAt":1722863459475,"runId":"run_86c2f1428b494e6f9797cc5a6e2ed33f","startedAt":1722862859475,"statusEnum":"in_progress","threadId":"thread_message_e2c3bd6bbc074c56bde4371191af88d0"}
event:thread.message.created
data:{"createAt":1722862861124,"message":{"content":"","contentType":"text","role":"assistant"},"messageId":"message_75c25f6c8cd847d4b1971e5765b59486","threadId":"thread_message_e2c3bd6bbc074c56bde4371191af88d0"}
event:thread.message.delta
data:{"mode":"overwrite","delta":{"role":"assistant","text":{"value":"你好"},"type":"text"},"messageId":"message_75c25f6c8cd847d4b1971e5765b59486"}
event:thread.message.delta
data:{"mode":"overwrite","delta":{"role":"assistant","text":{"value":"你好！"},"type":"text"},"messageId":"message_75c25f6c8cd847d4b1971e5765b59486"}
event:thread.message.delta
data:{"mode":"overwrite","delta":{"role":"assistant","text":{"value":"你好！有什么"},"type":"text"},"messageId":"message_75c25f6c8cd847d4b1971e5765b59486"}
event:thread.message.delta
data:{"mode":"overwrite","delta":{"role":"assistant","text":{"value":"你好！有什么可以帮助你的吗？比如"},"type":"text"},"messageId":"message_75c25f6c8cd847d4b1971e5765b59486"}
event:thread.message.delta
data:{"mode":"overwrite","delta":{"role":"assistant","text":{"value":"你好！有什么可以帮助你的吗？比如查询某个地方的天气。&&Next"},"type":"text"},"messageId":"message_75c25f6c8cd847d4b1971e5765b59486"}
event:thread.message.delta
data:{"mode":"overwrite","delta":{"role":"assistant","text":{"value":"你好！有什么可以帮助你的吗？比如查询某个地方的天气。"},"type":"text"},"messageId":"message_75c25f6c8cd847d4b1971e5765b59486"}
event:thread.message.delta
data:{"mode":"overwrite","delta":{"role":"assistant","text":{"value":"你好！有什么可以帮助你的吗？比如查询某个地方的天气。"},"type":"text"},"messageId":"message_75c25f6c8cd847d4b1971e5765b59486"}
event:thread.message.delta
data:{"mode":"overwrite","delta":{"role":"assistant","text":{"value":"你好！有什么可以帮助你的吗？比如查询某个地方的天气。"},"type":"text"},"messageId":"message_75c25f6c8cd847d4b1971e5765b59486"}
event:thread.message.completed
```

## **最佳实践**

### **非流式调用示例**

```java
public class AssistantRunService {
    private static final String APP_ACCESS_TOKEN = "${your_access_token}";
    private static final String ASSISTANT_ID = "${your_assistant_id}";

    public String createThread() {
        RestTemplate restTemplate = new RestTemplate();

        HttpHeaders httpHeaders = new HttpHeaders();
        httpHeaders.setContentType(MediaType.APPLICATION_JSON);
        httpHeaders.set("x-acs-dingtalk-access-token", APP_ACCESS_TOKEN);
        HttpEntity request = new HttpEntity<>(httpHeaders);
        ResponseEntity response = restTemplate.postForEntity("https://api.dingtalk.com/v1.0/assistant/threads", request, JSONObject.class);
        if (!Objects.equals(response.getStatusCode(), HttpStatus.OK)) {
            // TODO 调用接口失败的场景处理，做对应的异常业务处理
            throw new RuntimeException("create thread http response status is not ok");
        }

        JSONObject body = response.getBody();
        if (body == null) {
            // TODO 接口未返回任何内容，做对应的异常业务处理
            throw new RuntimeException("create thread http response body is invalid");
```

### 流式调用示例

```java
public class AssistantRunStreamService {
    private static final String APP_ACCESS_TOKEN = "${your_access_token}";
    private static final String ASSISTANT_ID = "${your_assistant_id}";

    public String createThread() {
        RestTemplate restTemplate = new RestTemplate();

        HttpHeaders httpHeaders = new HttpHeaders();
        httpHeaders.setContentType(MediaType.APPLICATION_JSON);
        httpHeaders.set("x-acs-dingtalk-access-token", APP_ACCESS_TOKEN);
        HttpEntity request = new HttpEntity<>(httpHeaders);
        ResponseEntity response = restTemplate.postForEntity("https://api.dingtalk.com/v1.0/assistant/threads", request, JSONObject.class);
        if (!Objects.equals(response.getStatusCode(), HttpStatus.OK)) {
            // TODO 调用接口失败的场景处理，做对应的异常业务处理
            throw new RuntimeException("create thread http response status is not ok");
        }

        JSONObject body = response.getBody();
        if (body == null) {
            // TODO 接口未返回任何内容，做对应的异常业务处理
            throw new RuntimeException("create thread http response body is invalid");
```

## **所属商业化版本**

钉钉 AI 生产力平台高级版和定制版。