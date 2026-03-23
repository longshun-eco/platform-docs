---
title: "API 调用示例"
source: "https://open.dingtalk.com/document/development/example-of-calling-the-card-api-interface"
category: "服务端API / 互动卡片 / 示例与工具"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-example-of-calling-the-card-api-interface_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-example-of-calling-the-card-api-interface_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23由于创建卡片、投放卡片接口参数比较复杂，本文档提供常见的参数组合和各语言调用示例以作参考。

## **创建并投放卡片（发送卡片）接口调用示例**

下面是三个常用场域的创建并投放卡片（发送卡片）接口调用传参示例，示例中花括号的内容需要替换成真实的数据，比如 access\_token、卡片模板 id、用户 userId、群聊 openConversationId 等。[创建卡片](/document/development/interface-for-creating-a-card-instance)和[投放卡片](/document/development/delivery-card-interface)接口的传参也可参考该示例。

### **场域类型：****IM机器人单聊**

HTTP

```
POST /v1.0/card/instances/createAndDeliver HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "cardTemplateId": "{卡片模板 id}",
  "outTrackId": "{唯一卡片实例 id}",
  "cardData": {
    "cardParamMap": {
      "string": "字符串",
      "boolean": "true",
      "number": "1",
      "markdown": "# markdown",
      "obj": "{\"key\": \"value\"}",
      "arr": "[{\"key\": \"value\"}]"
    }
  },
  "openSpaceId": "dtv1.card//IM_ROBOT.{用户 userId}",
  "imRobotOpenSpaceModel": { "supportForward": true },
  "imRobotOpenDeliverModel": { "spaceType": "IM_ROBOT" }
```

Java

```java
import com.alibaba.fastjson.JSON;
```

Python

```
import uuid
```

Node.js

```javascript
const axios = require('axios');
```

Go

```go
package main
```

### **场域类型：IM机器人群聊**

HTTP

```
POST /v1.0/card/instances/createAndDeliver HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "cardTemplateId": "{卡片模板 id}",
  "outTrackId": "{唯一卡片实例 id}",
  "cardData": {
    "cardParamMap": {
      "string": "字符串",
      "boolean": "true",
      "number": "1",
      "markdown": "# markdown",
      "obj": "{\"key\": \"value\"}",
      "arr": "[{\"key\": \"value\"}]"
    }
  },
  "imGroupOpenSpaceModel": { "supportForward": true },
  "openSpaceId": "dtv1.card//IM_GROUP.{群聊 openConversationId}",
  "imGroupOpenDeliverModel": { "robotCode": "{应用 client-id}" }
```

Java

```java
import com.alibaba.fastjson.JSON;
```

Python

```
import uuid
```

Node.js

```javascript
const axios = require('axios');
```

Go

```go
package main
```

### **场域类型：吊顶**

HTTP

```
POST /v1.0/card/instances/createAndDeliver HTTP/1.1
Host:api.dingtalk.com
x-acs-dingtalk-access-token:String
Content-Type:application/json

{
  "cardTemplateId": "{卡片模板 id}",
  "outTrackId": "{唯一卡片实例 id}",
  "cardData": {
    "cardParamMap": {
      "string": "字符串",
      "boolean": "true",
      "number": "1",
      "markdown": "# markdown",
      "obj": "{\"key\": \"value\"}",
      "arr": "[{\"key\": \"value\"}]"
    }
  },
  "openSpaceId": "dtv1.card//ONE_BOX.{群聊 openConversationId}",
  "topOpenSpaceModel": { "spaceType": "ONE_BOX" },
  "topOpenDeliverModel": { "expiredTimeMillis": 1739795765042 }
```

Java

```java
import com.alibaba.fastjson.JSON;
```

Python

```
import uuid
```

Node.js

```javascript
const axios = require('axios');
```

Go

```go
package main
```

## **相关文档**

* [创建并投放卡片](/document/development/create-and-deliver-cards)