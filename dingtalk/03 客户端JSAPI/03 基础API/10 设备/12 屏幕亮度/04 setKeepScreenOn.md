---
title: "setKeepScreenOn"
source: "https://open.dingtalk.com/document/development/jsapi-set-keep-screen-on"
category: "客户端JSAPI / 基础API / 设备 / 屏幕亮度"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-set-keep-screen-on_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-set-keep-screen-on_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用setKeepScreenOn，设置屏幕常亮。

注意：H5容器关闭后自动失效。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 5.1.26 | 5.1.26 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11622) |
| 小程序 | 7.0.10 | 7.0.10 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11622) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

在H5应用中，调用[dd.config](https://open.dingtalk.com/document/orgapp/jsapi-authentication)完成鉴权后使用

在小程序应用中，无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| isKeep | Boolean | 是 | true | 是否保持常亮，默认值false。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```java
dd.setKeepScreenOn({
  isKeep: true,
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```