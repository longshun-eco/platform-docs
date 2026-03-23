---
title: "将描述画到画布中(draw)"
source: "https://open.dingtalk.com/document/development/canvascontext-draw"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-draw_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-draw_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.draw**将之前在绘图上下文中的描述（路径、变形、样式）画到 canvas 中。

**重要**

绘图上下文需要由 `dd.createCanvasContext(canvasId)` 来创建。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.setFillStyle('blue');
ctx.fillRect(20, 20, 180, 80);
ctx.draw();
ctx.fillRect(60, 60, 250, 120);
ctx.draw(true);
```

## **入参**

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| reserve | Boolean | 本次绘制是否接着上一次绘制，默认为false。   * 参数为 false 时，则在本次调用 drawCanvas绘制之前 native 层应先清空画布再继续绘制。 * 参数为true 时，则保留当前画布上的内容，本次调用drawCanvas绘制的内容覆盖在上面。 |