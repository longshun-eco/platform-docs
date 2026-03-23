---
title: "企业内部机器人实现群聊发送Markdown消息"
source: "https://open.dingtalk.com/document/development/enterprise-internal-robots-send-markdown-messages"
category: "服务端API / 历史文档（不推荐） / 即时通信IM / 机器人 / 使用教程"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-enterprise-internal-robots-send-markdown-messages_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-enterprise-internal-robots-send-markdown-messages_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-14本示例介绍了企业内部机器人使用Webhook方式，实现发送Markdown消息。Markdown语法支持的类型有标题、引用、文字效果、链接、图片、无序列表和有序列表。

## 本文适用对象

* 新手开发者，希望了解钉钉企业内部机器人群聊发送Markdown消息的语法。
* 正在开发应用的开发者，希望了解钉钉企业内部机器人群聊发送Markdown消息的语法及发送消息的流程。

## 适用场景

使用机器人的**Webhook方式**发送机器人消息。

## 注意事项

机器人使用Markdown语法@人员，不支持高亮显示。

**说明**

例如下图所示，使用Markdown语法发送的@小齐未高亮。

![[development-enterprise-internal-robots-send-markdown-messages_p384990.png]]

## 支持的Markdown语法

```
标题
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

引用
> A man who stands for nothing will fall for anything.

文字加粗、斜体
**bold**
*italic*

链接
[this is a link](https://www.dingtalk.com/)

图片
![[development-enterprise-internal-robots-send-markdown-messages_pic.jpg]]
```

## 接入流程简介

步骤一：登录[开发者后台](https://open-dev.dingtalk.com/#/)，点击应用开发-企业内部开发，创建[机器人](https://open.dingtalk.com/document/orgapp/enterprise-created-chatbot)。

步骤二：点击机器人应用-基础信息，获取AppKey和AppSecret。

步骤三：设置开发管理，添加消息接收地址。

步骤四：上线机器人。进入版本管理与发布页面，点击上线，机器人的状态变更为已发布。

步骤五：在机器人所在的企业，创建一个企业内部群。如已有该企业的企业内部群，此步骤可跳过。

步骤六：添加机器人到企业内部群。

## 步骤一：创建企业内部机器人

登录[开发者后台](https://open-dev.dingtalk.com/#/)，点击应用开发-企业内部开发，创建[机器人](https://open.dingtalk.com/document/orgapp/enterprise-created-chatbot)。

![[development-enterprise-internal-robots-send-markdown-messages_p385216.png]]

## 步骤二：获取AppKey和AppSecret

获取机器人AppKey和AppSecret。

![[development-enterprise-internal-robots-send-markdown-messages_p385218.png]]

## 步骤三：设置开发管理

设置开发管理，添加消息接收地址。

**说明**

消息接收地址是指@群机器人时，将消息发送到指定服务端地址。详情请参考文档[接收消息的消息协议](https://open.dingtalk.com/document/orgapp/receive-message-2)。

![[development-enterprise-internal-robots-send-markdown-messages_p385219.png]]

## 步骤四：发布机器人

上线机器人。进入版本管理与发布页面，点击上线，机器人的状态变更为已发布。

**说明**

点击“调试”所进入的测试群“xxxxxxxxx-TEST”@机器人无法获取当前人员的senderStaffId，即当前人员的userId，请使用以下创建企业内部群的方式测试机器人。

![[development-enterprise-internal-robots-send-markdown-messages_p385221.png]]

## 步骤五：创建企业内部群

在机器人所在的企业，创建一个企业内部群。如已有该企业的企业内部群，此步骤可跳过。

**说明**

例如“机器人”所在企业为“测试组织演示”，创建企业内部群必须为“测试组织演示[内部群]”。

![[development-enterprise-internal-robots-send-markdown-messages_p385223.png]]

![[development-enterprise-internal-robots-send-markdown-messages_p384754.png]]

## 步骤六：添加机器人

添加机器人到企业内部群。

![[development-enterprise-internal-robots-send-markdown-messages_p385227.png]]

## 场景一：发送标题语法的markdown消息并实现@人员

### 预期效果

![[development-enterprise-internal-robots-send-markdown-messages_p384640.png]]

### 示例代码

```java
package com.dingtalk;

import com.alibaba.fastjson.JSON;
import com.alibaba.fastjson.JSONObject;
import com.dingtalk.api.DefaultDingTalkClient;
import com.dingtalk.api.DingTalkClient;
import com.dingtalk.api.request.OapiRobotSendRequest;
import com.dingtalk.api.response.OapiRobotSendResponse;
import com.taobao.api.ApiException;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;

import java.util.Arrays;

@RestController
public class RobotsController3 {
    private static final String TITLE = "标题";

    /**
```

## 场景二：发送引用语法的markdown消息并实现@人员

### 预期效果

![[development-enterprise-internal-robots-send-markdown-messages_p384643.png]]

### 示例代码

```java
package com.dingtalk;

import com.alibaba.fastjson.JSON;
import com.alibaba.fastjson.JSONObject;
import com.dingtalk.api.DefaultDingTalkClient;
import com.dingtalk.api.DingTalkClient;
import com.dingtalk.api.request.OapiRobotSendRequest;
import com.dingtalk.api.response.OapiRobotSendResponse;
import com.taobao.api.ApiException;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;

import java.util.Arrays;

@RestController
public class RobotsController3 {
    private static final String QUOTE = "引用";

    /**
```

## 场景三：发送文字加粗、斜体语法的markdown消息并实现@人员

### 预期效果

![[development-enterprise-internal-robots-send-markdown-messages_p384663.png]]

### 示例代码

```java
package com.dingtalk;

import com.alibaba.fastjson.JSON;
import com.alibaba.fastjson.JSONObject;
import com.dingtalk.api.DefaultDingTalkClient;
import com.dingtalk.api.DingTalkClient;
import com.dingtalk.api.request.OapiRobotSendRequest;
import com.dingtalk.api.response.OapiRobotSendResponse;
import com.taobao.api.ApiException;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;

import java.util.Arrays;

@RestController
public class RobotsController3 {
    private static final String TYPEFACE = "字体";

    /**
```

## 场景四：发送链接语法的markdown消息并实现@人员

### 预期效果

![[development-enterprise-internal-robots-send-markdown-messages_p384686.png]]

### 示例代码

```java
package com.dingtalk;

import com.alibaba.fastjson.JSON;
import com.alibaba.fastjson.JSONObject;
import com.dingtalk.api.DefaultDingTalkClient;
import com.dingtalk.api.DingTalkClient;
import com.dingtalk.api.request.OapiRobotSendRequest;
import com.dingtalk.api.response.OapiRobotSendResponse;
import com.taobao.api.ApiException;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;

import java.util.Arrays;

@RestController
public class RobotsController3 {
    private static final String LINK = "链接";

    /**
```

## 场景五：发送图片语法的markdown消息并实现@人员

### 预期效果

![[development-enterprise-internal-robots-send-markdown-messages_p384717.png]]

### 示例代码

```java
package com.dingtalk;

import com.alibaba.fastjson.JSON;
import com.alibaba.fastjson.JSONObject;
import com.dingtalk.api.DefaultDingTalkClient;
import com.dingtalk.api.DingTalkClient;
import com.dingtalk.api.request.OapiRobotSendRequest;
import com.dingtalk.api.response.OapiRobotSendResponse;
import com.taobao.api.ApiException;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;

import java.util.Arrays;

@RestController
public class RobotsController3 {
    private static final String IMAGE = "图片";

    /**
```

## 场景六：发送有序列表语法的markdown消息并实现@人员

### 预期效果

![[development-enterprise-internal-robots-send-markdown-messages_p384734.png]]

### 示例代码

```java
package com.dingtalk;

import com.alibaba.fastjson.JSON;
import com.alibaba.fastjson.JSONObject;
import com.dingtalk.api.DefaultDingTalkClient;
import com.dingtalk.api.DingTalkClient;
import com.dingtalk.api.request.OapiRobotSendRequest;
import com.dingtalk.api.response.OapiRobotSendResponse;
import com.taobao.api.ApiException;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;

import java.util.Arrays;

@RestController
public class RobotsController3 {
    private static final String SORTEDLIST = "有序列表";

    /**
```

## 场景七：发送无序列表语法的markdown消息并实现@人员

### 预期效果

![[development-enterprise-internal-robots-send-markdown-messages_p384740.png]]

### 示例代码

```java
package com.dingtalk;

import com.alibaba.fastjson.JSON;
import com.alibaba.fastjson.JSONObject;
import com.dingtalk.api.DefaultDingTalkClient;
import com.dingtalk.api.DingTalkClient;
import com.dingtalk.api.request.OapiRobotSendRequest;
import com.dingtalk.api.response.OapiRobotSendResponse;
import com.taobao.api.ApiException;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;

import java.util.Arrays;

@RestController
public class RobotsController3 {
    private static final String UNSORTEDLIST = "无序列表";

    /**
```