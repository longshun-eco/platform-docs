---
title: "CanvasContext.draw"
source: "https://open.dingtalk.com/document/development/jsapi-canvas-context-draw"
category: "客户端JSAPI / 基础API / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-canvas-context-draw_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-canvas-context-draw_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用CanvasContext.draw，将之前在绘图上下文中的描述（路径、变形、样式）画到 canvas 中。

> 绘图上下文需要由 dd.createCanvasContext(canvasId) 来创建。

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.setFillStyle('blue');
ctx.fillRect(20, 20, 180, 80);
ctx.draw();
ctx.fillRect(60, 60, 250, 120);
ctx.draw(true);
```

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10090) |

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
| reserve | Boolean | 是 | false | 本次绘制是否接着上一次绘制，默认为false：   * 参数为 false 时，则在本次调用 drawCanvas绘制之前 native 层应先清空画布再继续绘制。 * 参数为true 时，则保留当前画布上的内容，本次调用drawCanvas绘制的内容覆盖在上面。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.CanvasContext.draw({
  reserve: false,
});
```