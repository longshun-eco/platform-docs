---
title: "rotateScreenView"
source: "https://open.dingtalk.com/document/development/jsapi-rotate-screen-view"
category: "客户端JSAPI / 基础API / 设备 / 设备方向"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-rotate-screen-view_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-rotate-screen-view_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用rotateScreenView，旋转屏幕。

旋转屏幕视图到横屏状态，并隐藏页面导航栏。开发者在使用此JSAPI后，需要提供重置按钮，保证用户可以返回竖屏状态或退出页面。

> 本接口不支持iPad上的旋转屏幕。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11668) |
| 小程序 | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |

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
| clockwise | Boolean | 是 | true | 是否为顺时针方向旋转，默认 true。 |
| showStatusBar | Boolean | 是 | true | 是否显示statusbar (iOS)。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.rotateScreenView({
  clockwise: true,
  showStatusBar: true,
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```