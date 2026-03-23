---
title: "客户端API总览"
source: "https://open.dingtalk.com/document/dingstart/webapp-jsapi-overview"
category: "新手指南 / 开发网页应用"
updated: 
tags:
  - dingtalk
  - 新手指南
---
![[dingstart-webapp-jsapi-overview_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[dingstart-webapp-jsapi-overview_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22本SDK适用于钉钉小程序、H5微应用开发者，提供在钉钉客户端内调用原生能力的JavaScript接口。

## **引入方式**

### **方式一：使用npm引入（推荐）**

1. 使用npm安装。

   ```bash
   npm install dingtalk-jsapi --save
   ```

   > dingtalk-jsapi 3.0.27 版本后支持一段式，例如：chooseChat，同时也支持三段式，例如：biz.contact.choose。
2. 加载 dingtalk-jsapi：

   ```
   import * as dd from 'dingtalk-jsapi'; // 此方式为整体加载，也可按需进行加载
   ```

### **方式二：使用cdn引入（不推荐）**

浏览器引入，在浏览器中使用 script 和 link 标签直接引入文件，并使用全局变量 dd。

**说明**

不推荐使用浏览器引入方法，这样无法按需加载，而且难以获得底层依赖模块的 bug 快速修复支持。

## **使用示例**

通过上方提供的两种方式，在前端引用客户端SDK后，即可调用客户端提供的相关JSAPI的能力，客户端JSAPI总览可参考[客户端API总览](/document/development/jsapi-overview)。

以下，我们提供了关于免登、调用界面API设置标题、调用位置API获取当前位置的示例，仅供参考：

```java
// 示例：完整的小程序初始化与API调用流程
import * as dd from 'dingtalk-jsapi';

// 1. 获取免登授权码
dd.getAuthCode({
  corpId: 'your_corp_id',
  onSuccess: (res) => {
    const authCode = res.authCode;
    console.log('获取authCode:', authCode);
    // 发送到服务端换取用户身份信息
  },
  onFail: (err) => {
    console.error('获取authCode失败:', err);
  }
});

// 2. 调用界面API设置标题
dd.setNavigationTitle({
  title: '我的页面'
});
```