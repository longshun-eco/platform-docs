---
title: "setNavigationBar"
source: "https://open.dingtalk.com/document/development/jsapi-set-navigation-bar"
category: "客户端JSAPI / 基础API / 界面 / 导航栏"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-set-navigation-bar_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-set-navigation-bar_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用setNavigationBar，设置导航栏。

> 设置小程序导航栏样式及标题等。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10048) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| title | String | 是 | 你好 | 导航栏标题。 |
| backgroundColor | String | 是 | #108ee9 | 导航栏背景色，支持十六进制颜色值。 |
| reset | Boolean | 是 | false | 是否重置导航栏为钉钉默认配色。 默认值： false。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```java
dd.setNavigationBar({
  reset: false,
  title: '你好',
  backgroundColor: '#108ee9',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```