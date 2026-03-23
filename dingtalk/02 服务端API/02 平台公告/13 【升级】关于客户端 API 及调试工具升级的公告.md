---
title: "【升级】关于客户端 API 及调试工具升级的公告"
source: "https://open.dingtalk.com/document/development/client-api-upgradation-announcement"
category: "服务端API / 平台公告"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-client-api-upgradation-announcement_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-client-api-upgradation-announcement_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-21为了更好地帮助开发者学习和使用钉钉客户端 API， 我们对客户端 API 在开发方式、文档架构和调试方式进行了全新升级，帮助开发者更加便捷、高效地开发客户端应用。

## **升级详情**

### **开发方式**

客户端 API 的调用方式从三段式调用统一升级为一段式调用。升级后，无论开发小程序还是 H5 微应用，你都可以使用同一种接口调用方式调用客户端 API，无需学习和适应不同的调用方式。关于新旧版客户端 API 对比详情，参考[新旧版客户端 API 对比](https://open.dingtalk.com/document/orgapp/client-api-comparison-table)。

* **旧版客户端 API：三段式**

  ```javascript
  dd.device.notification.alert({
      message: "测试",
      title: "提示",//可传空
      buttonName: "收到",
      onSuccess : function() {
          //onSuccess将在点击button之后回调
          /*回调*/
      },
      onFail : function(err) {}
  });
  ```
* **新版客户端 API：一段式**

  ```
  dd.alert({
    title: '消息提示',
    content: '请求发布成功',
    buttonText: '我知道了',
    success: () => {},
    fail: () => {},
    complete: () => {},
  });
  ```

### 调试工具

客户端 API 调试工具全面支持小程序和 H5 微应用两种应用类型的客户端 API 调试。你可以轻松地在客户端 API 调试工具中进行小程序和 H5 微应用页面的调试，无需再编写代码。

## 变更影响

* **旧版客户端 API**：如你已使用旧版客户端 API，此次升级不会影响正常使用。但旧版客户端 API 仅保持现有功能，不再新增支持其他能力。推荐使用[新版客户端API](https://open.dingtalk.com/document/orgapp/jsapi-overview-client-org)。
* **旧版客户端调试工具下线时间**：预计于 2023 年 11 月 1 日正式下线。推荐使用[新版客户端调试工具](https://open.dingtalk.com/tools/explorer/jsapi?id=10307)。

## **常见问题**

* **新版是否兼容旧版？**

  答：新版客户端 SDK 全面兼容旧版，旧版能力可以正常使用，但客户端后续的新增开放能力仅支持一段式调用。
* **切换到新版调试工具后，是否可以返回？**

  答：可以，旧版客户端调试工具预计于 2023 年 11 月 1 日正式下线，推荐尽快切换[新版客户端调试工具](https://open.dingtalk.com/tools/explorer/jsapi?id=10307)。
* **新版客户端 SDK 如何引入？**

  答：使用`npm install dingtalk-jsapi --save`命令，即可引入最新版客户端 SDK 。

**如果你对本次变更有任何疑问或建议，随时联系我们的**[**技术支持团队**](https://open.dingtalk.com/document/contactus/ngliko)**。**