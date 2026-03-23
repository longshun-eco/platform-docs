---
title: "服务端SDK下载"
source: "https://open.dingtalk.com/document/development/download-the-server-side-sdk"
category: "服务端API / 使用帮助"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-download-the-server-side-sdk_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-download-the-server-side-sdk_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-03-11钉钉官方提供了统一的SDK，使用SDK可以便捷地调用服务端API。

**重要**

* 新旧版服务端的接口需要单独下载各自版本的SDK，且一个项目中SDK可以共存，但两者不能相互调用，新版的接口只能用新版SDK调用，旧版接口只能用旧版SDK调用，如何区分新旧版接口可以参考[旧版服务端API、新版服务端API的区别](/document/development/how-to-call-apis#section-8lr-id4-rbz)。
* 我们对接口的返回字段做了简化处理，如果字段的值为空或者null，那么将不返回该字段。

## 新版SDK vs 旧版SDK

|  |  |  |
| --- | --- | --- |
| **对比维度** | **新版服务端SDK** | **旧版服务端SDK** |
| 架构基础 | 基于阿里云OpenAPI规范构建 | 基于早期自研架构设计 |
| 接口支持范围 | 支持新版API，路径不含`/topapi/` | 仅支持旧版API，路径含 `/topapi/` |
| 推荐使用场景 | 所有新项目优先选用 | 兼容历史系统、维护老接口调用 |
| 多语言支持 | Java、Go、C#、PHP、Node.js、Python等 | Java、PHP、Python、.NET、Node等 |
| 性能与稳定性 | 更优、签名标准化 | 稳定，但部分功能需手动实现 |
| 迁移路径 | 旧版接口逐步迁移至新版，推荐长期使用新版 | 不建议新增依赖，已有系统可继续维护 |

**说明**

若您正在开发新应用，请优先选择**新版服务端SDK**；如需调用包含 `/topapi/` 路径的接口，则应使用**旧版SDK**。

## 新版服务端SDK

新版SDK基于阿里云OpenAPI规范构建，推荐新项目优先使用。支持多语言接入，可通过包管理工具快速集成。

### **请求示例**

新版SDK与旧版SDK有所差别，新版SDK如何使用可以参考[如何调用服务端API](/document/development/how-to-call-apis)文档说明。以下是关于新版接口的使用示例，以创建日程为例：

```java
  /**
     * 使用 Token 初始化账号Client
     * @return Client
     * @throws Exception
     */
    public static com.aliyun.dingtalkcalendar_1_0.Client createClient() throws Exception {
        com.aliyun.teaopenapi.models.Config config = new com.aliyun.teaopenapi.models.Config();
        config.protocol = "https";
        config.regionId = "central";
        return new com.aliyun.dingtalkcalendar_1_0.Client(config);
    }

    public static void main(String[] args_) throws Exception {
        java.util.List args = java.util.Arrays.asList(args_);
        com.aliyun.dingtalkcalendar_1_0.Client client = Sample.createClient();
        com.aliyun.dingtalkcalendar_1_0.models.CreateEventHeaders createEventHeaders = new com.aliyun.dingtalkcalendar_1_0.models.CreateEventHeaders();
        createEventHeaders.xAcsDingtalkAccessToken = "";
        com.aliyun.dingtalkcalendar_1_0.models.CreateEventRequest.CreateEventRequestRichTextDescription richTextDescription = new com.aliyun.dingtalkcalendar_1_0.models.CreateEventRequest.CreateEventRequestRichTextDescription()
                .setText("

测试测试

热热热

单独的

啊啊啊

事实上

");
        com.aliyun.dingtalkcalendar_1_0.models.CreateEventRequest.CreateEventRequestUiConfigs uiConfigs0 = new com.aliyun.dingtalkcalendar_1_0.models.CreateEventRequest.CreateEventRequestUiConfigs()
                .setUiName("updateEventButton")
```

其他语言示例代码，可参考具体接口文档中的**示例**模块，我们提供了HTTP、Java、Python、PHP、Go、Node.js、C#等多种方式调用。

### **SDK 下载与依赖**

* **Java**

  **方式一**：通过Maven安装DingTalk OpenAPI Java SDK

  添加依赖项到`pom.xml`的文件中，建议始终使用最新版本以获得功能更新与安全修复，最新的SDK版本可以在[这里](https://central.sonatype.com/artifact/com.aliyun/dingtalk)查看。

  **说明**

  截止 2026 年 03 月 10 日，最新版本为 2.2.44，开发者请选择使用 SDK 最新版本。

  ```
   com.aliyun
   dingtalk
   {version}
  ```

  **方式二**：通过下载[**SDK安装包**](https://open-dev.dingtalk.com/sdk/download/java)进行安装。
* **Go**

  在命令行中，执行以下命令安装DingTalk OpenAPI Go SDK。

  ```
  go get -u github.com/alibabacloud-go/dingtalk/
  ```
* **C#**

  **方式一：**使用`dotnet`来安装C# SDK，最新的SDK版本可以在[这里](https://www.nuget.org/packages/AlibabaCloud.SDK.Dingtalk)查看。

  ```
  dotnet add package AlibabaCloud.SDK.Dingtalk
  ```

  **方式二**：通过下载[**SDK安装包**](https://open-dev.dingtalk.com/sdk/download/csharp)进行安装。
* **PHP**

  **方式一：**使用composer工具进行安装。

  ```
  composer require alibabacloud/dingtalk
  ```

  **方式二**：通过下载[**SDK安装包**](https://open-dev.dingtalk.com/sdk/download/composer)进行安装。
* **Node.js**

  **方式一：**执行以下命令，使用npm安装依赖。

  ```bash
  npm install @alicloud/dingtalk --save
  ```

  **方式二**：通过下载[**SDK安装包**](https://open-dev.dingtalk.com/sdk/download/nodejs)进行安装。
* **Python**

  **方式一：**执行以下命令，使用pip安装包依赖。

  ```bash
  pip install alibabacloud_dingtalk
  ```

  **方式二**：通过下载[**SDK安装包**](https://open-dev.dingtalk.com/sdk/download/python)进行安装，Python SDK适用于Python 3.0及以上版本。

## 旧版服务端SDK

旧版SDK基于早期架构设计，仅用于兼容历史接口（URL包含 `/topapi/`）。新项目建议使用新版SDK。

### 请求示例

下面是使用SDK调用API的请求示例：

* Java

  ```java
  DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/user/get");
  OapiUserGetRequest req = new OapiUserGetRequest();
  req.setUserid("userid1");
  req.setHttpMethod("GET");
  OapiUserGetResponse rsp = client.execute(req, accessToken);
  ```
* PHP

  ```java
  include "TopSdk.php";
  // DingTalkConstant::$METHOD_GET 要与下面调用接口url要求的保持一致
  $c = new DingTalkClient(DingTalkConstant::$CALL_TYPE_OAPI, DingTalkConstant::$METHOD_GET , DingTalkConstant::$FORMAT_JSON);
  $req = new OapiUserGetRequest();
  $req->setUserid("userid1");
  $resp=$c->execute($req, $accessToken,"https://oapi.dingtalk.com/user/get");
  var_dump($resp)
  ```
* Python

  ```
  import dingtalk.api
  request = dingtalk.api.OapiGettokenRequest("https://oapi.dingtalk.com/user/get")
  request.userid="userid1"
  response = request.getResponse()
  print(response)
  ```
* Node

  ```java
  let { Config, OapiProcessinstanceGetParams, OapiProcessinstanceGetRequest } = require('./client.js');
  let Client = require('./client.js').default
  // import Client,{ Config, GetOapiProcessinstanceParams, GetOapiProcessinstanceRequest } from "./client.js";
  async function test() {
    const config = new Config()
    config.serverUrl = 'https://oapi.dingtalk.com/topapi/processinstance/get'
    config.session = 'access_token'
    const params = new OapiProcessinstanceGetParams();
    params.processInstanceId = '23aa6xxxxc1b56c'

    const request = new OapiProcessinstanceGetRequest()
    request.params = params
    const client = new Client(config)
    try {
      const res = await client.oapiProcessinstanceGet(request)
      console.log(res.body)
    } catch (err) {
      console.log(err)
    }
  }
  test()
  ```
* .NET

  ```java
  IDingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/user/get");
  OapiUserGetRequest req = new OapiUserGetRequest();
  req.Userid = "userid1";
  req.SetHttpMethod("GET");
  // accessToken 参数是需要通过https://open.dingtalk.com/document/development/obtain-orgapp-token接口获取
  OapiUserGetResponse rsp = client.Execute(req, access_token)
  ```

**请求示例说明**：

1. **初始化Client对象**：设置目标接口的完整URI。通常无需手动拼接 `access_token` 等参数；但部分POST接口可能需在URL中附加非token类参数。
2. **构造Request对象**：命名规则一般为 `Oapi + 接口路径驼峰形式 + Request`。例如 `/user/get` 对应 `OapiUserGetRequest`。
3. **设置请求参数**：调用对应setter方法赋值。注意默认HTTP方法为POST，若接口为GET，需显式调用 `setHttpMethod("GET")`。
4. **执行请求**：调用 `client.execute(req, access_token)` 发起调用。对于获取token类接口（如 `/gettoken`、`/sns/gettoken`、`/service/get_suite_token`），调用时无需传入token。
5. **处理响应**：返回结果为与Request对应的Response对象，可从中提取业务数据或错误信息。

### SDK下载与依赖

#### **环境依赖**

* Java SDK 需要依赖 Java SE/EE 1.5及以上
* .NET SDK 需要依赖 .NET Framework 2.0及以上 （不支持Windows Phone平台）

#### 下载地址

* Java版本：

  + JAR包下载：[点击下载](https://open-dev.dingtalk.com/download/openSDK/java)
  + 添加maven依赖：

    ```
        com.aliyun
        alibaba-dingtalk-service-sdk
        2.0.0
    ```
* PHP版本：[点击下载](https://open-dev.dingtalk.com/download/openSDK/php)
* Python版本：[点击下载](https://open-dev.dingtalk.com/download/openSDK/python)
* Python3版本：[点击下载](https://open-dev.dingtalk.com/download/openSDK/python3)
* .NET版本：[点击下载](https://open-dev.dingtalk.com/download/openSDK/cshap)
* .NET Core版本：[点击下载](https://open-dev.dingtalk.com/download/openSDK/netCore)
* Node版本：[点击下载](https://icms-document.oss-cn-beijing.aliyuncs.com/nodeSDK/dingtalk-sdk-nodejs.zip?versionId=CAEQGBiBgMD5xfDg7RciIDQ2MDYxNTc0NDMyODRkY2FhYjI2OGE3MDBhNmYyMTgz)