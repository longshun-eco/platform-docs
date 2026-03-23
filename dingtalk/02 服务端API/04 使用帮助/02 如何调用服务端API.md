---
title: "如何调用服务端API"
source: "https://open.dingtalk.com/document/development/how-to-call-apis"
category: "服务端API / 使用帮助"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-how-to-call-apis_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-how-to-call-apis_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-08本文介绍钉钉开放平台新旧版本服务端API的差异，帮助开发者理解不同规范下的接口调用方式，并根据实际应用场景选择合适的API进行接入。

## 旧版服务端API、新版服务端API的区别

为提升接口使用体验并提供更规范的开发标准，钉钉开放平台对服务端API进行了规范升级。目前平台同时支持旧版服务端API（基于旧版规范）和新版服务端API（基于新版RESTful风格规范）。建议新应用优先接入新版API以获得持续的能力更新和技术支持。

**说明**

旧版服务端API与新版服务端API所开放的产品能力不完全一致。请根据业务需求选择合适的API版本。已有应用可继续使用旧版API，但新增功能推荐使用新版API。

|  |  |  |
| --- | --- | --- |
| API版本 | 旧版服务端API | 新版服务端API |
| 规范 | 旧版规范。 | 新版规范。 |
| SDK | 支持以下版本：Java、PHP、Python、.NET、.NET Core。 | 支持以下版本：Java（支持通过Maven安装）、Node.js、PHP、Go、C#、Python。 |
| 开放的产品能力 | * 现状：旧版服务端API和新版服务端API开放的产品能力不同，即新版服务端API未包含全部的服务端API的产品能力，请根据实际需求，选择需要的API接入。 * 计划：后续将逐步把旧版API迁移至新版规范，最终实现功能全覆盖。 | |
| 是否开放新能力 | 不再开放新能力。 | 持续开放新能力。 |
| 是否推荐 | 已接入的应用可继续使用，接口不会下线。 | 若新版本存在对应接口，推荐接入新版服务端API。 |

### **标识的差异**

* 旧版接口会在每个接口名称右侧添加“旧版SDK”标识，如下图所示：

  ![[development-how-to-call-apis_p1003889.png]]
* 新版接口会在每个新版接口名称右侧添加“新版SDK”标识，如下图所示：

  ![[development-how-to-call-apis_p1003890.png]]

### **文档格式差异**

#### 旧版文档格式说明

旧版API文档采用如下结构信息：

```
请求方式：GET/POST（HTTPS）
请求地址：https://oapi.dingtalk.com/gettoken?appkey=APP_KEY&appsecret=APP_SECRET
请求包体：
...
参数说明：
...
返回结果：
...
示例
...
```

* **请求方式**：接口使用的HTTP方法和请求协议。所有接口都使用HTTPS协议。
* **请求地址**：接口的请求地址。钉钉服务端接口的访问域名为`https://oapi.dingtalk.com`。请求参数使用“&”分隔。请求地址中的大写单词是需要替换的变量值。
* **请求包体/参数说明**：提供请求参数示例及说明，参数说明包括字段含义、取值范围，开发者在设计数据结构时，应参考该定义范围。
* **返回结果/参数说明**：提供返回参数示例及说明。

  **重要**
  + 所有接口在调用失败时都会返回**errcode**和**errmsg**。开发者可根据**errcode**和**errmsg**排查问题。
  + 请不要仅根据**errmsg**判断调用是否成功。当请求返回结果中返回了errcode且不为0时可判断为请求失败。**errmsg**是对**errcode**的说明，供开发者参考排查问题。
  + 我们对接口的返回字段做了简化处理，如果字段的值为空或者null，将不返回该字段。

#### 新版文档格式说明

新版API文档遵循RESTful设计规范，采用标准化结构呈现：

```
请求：
    权限
    请求方法
    Header参数
    Path参数
    Query参数
    Body参数
响应：
    返回参数
    返回示例
    错误码
```

调用 API 的详细入参说明，参数使用风格遵循 RESTFul，请注意不同参数在调用时的位置。

```json
{HTTP method} https://api.dingtalk.com/{version}/{resource}?{query-parameters}
```

* **请求方法**：`{HTTP method}`，API请求中使用的HTTP方法，支持以下方法：

  |  |  | | --- | --- | | 方法 | 说明 | | GET | 从资源中读取数据。 | | POST | 创建新的资源或执行某个操作。 | | PUT | 替换为新资源。 | | DELETE | 删除资源。 |
* **Header参数**：主要包含调用 API 所需要使用的访问凭证（access\_token）以及 HTTP Content-Type。
* **版本**：`{version}`，正在使用的API版本。DingTalk OpenAPI版本采用大版本号+小版本号组合的形式，例如1.0、2.1。

  + 小版本号升级（例如从1.0升级到1.1）意味着发布了不向后兼容的API升级。
  + 大版本号升级时（例如从1.0升级到2.0），上一个版本的API将在一段时间后停止支持。SDK和文档将取消上一个大版本API的入口。

    **重要**

    当大版本发布后，开发者需尽快升级至最新版本以便获得更好的支持。
* **Path参数**：`{resource}`，正在使用的资源，例如user, event等。这部分参数需要放置在 URL 中，在文档中一般以{ }表示。
* **Query参数**：`{query-parameters}`，这部分参数需要在 URL 后使用?进行连接，多个查询参数以&分割。
* **Body参数**：这部分参数需要放在 HTTP 请求的 Body 中，一般为 JSON 格式。
* **状态码**：表示成功或失败的HTTP状态码。
* **响应消息**：请求获取的数据或操作结果。某些操作，响应消息可能为空。

## 接口调用流程

1. 确保已经完成了钉钉开发者的注册与激活，并拥有子管理员和开发者权限，可以登录开发者后台。若尚未完成，请参考[获取开发者权限](/document/dingstart/get-developer-permissions)。
2. 确保了解钉钉开放平台基础概念，详情请参考[基础概念](/document/dingstart/basic-concepts-beta)，并了解了各产品块文档说明。
3. 确保你已了解调用频率限制。详情请参考[附录B：如何处理钉钉服务端API限流](/document/development/how-to-process-api-throttling-on-the-dingtalk-server)。
4. 创建应用，请根据[创建应用](/document/dingstart/create-application)创建对应的应用并获取应用凭证Clinet ID（原Appkey）和 Client Secret（原AppSecret）。

   ![[development-how-to-call-apis_p739915.png]]
5. 单击**开发配置** > **权限管理**，搜索**通讯录部门成员读权限**，并单击申请权限，详情请参考[添加接口调用权限](/document/development/add-api-permission)。
6. 根据不同版本的API，[下载服务端SDK](/document/development/download-the-server-side-sdk)。
7. 在调用服务端 API 前，根据Client ID和 Client Secret参数，调用下方接口获取 API 访问凭证accessToken。建议调用新版服务端API。

   * 新版服务端 API，详情请参考[新版-获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)。
   * 旧版服务端 API，详情请参考[旧版-获取企业内部应用的access\_token](/document/development/obtain-orgapp-token)。
8. 通过获取的accessToken调用各产品线相关接口，钉钉开放的服务端API，请参见[服务端API总览](/document/development/api-overview)。

   **说明**

   可以使用[服务端API调试工具](/document/download/api-explorer)进行接口调试和示例代码查看，
9. 查询服务端错误码表，了解排查建议。

   * 新版服务端 API，详情请参考[错误码（新版服务端）](/document/development/error-code)。
   * 旧版服务端 API，详情请参考[错误码（旧版服务端）](/document/development/server-api-error-codes-1)。
10. 通过事件订阅，钉钉向应用推送订阅的事件，例如通讯录变更等，详情请参考[事件订阅总览](/document/development/org-event-overview)。

## **接口调试工具**

钉钉开放平台为方便开发者调试体验API，为开发者提供了可视化在线API调用工具[服务端API调试工具](/document/download/api-explorer)，可实时查看API请求和返回结果。

## **新旧版SDK下载**

* 新版服务端API提供了Java、Node.js、PHP、Go、C#和Python 6种编程语言的SDK，详情请参考[新版服务端SDK](/document/development/download-the-server-side-sdk#section-3uc-c2m-3no)。
* 旧版服务端API提供了Java、PHP、Python、.NET SDK等供开发者使用，详情请参考[旧版服务端SDK](/document/development/download-the-server-side-sdk#section-q8u-97x-mxu)。