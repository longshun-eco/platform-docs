---
title: "创建矩形(rect)"
source: "https://open.dingtalk.com/document/development/canvascontext-rect"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-rect_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-rect_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.rect**创建一个矩形。

**重要**

用 `fill()` 或者 `stroke()` 方法将矩形画到 canvas 中。

## **示例代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.rect(20, 20, 250, 80);
ctx.setFillStyle('blue');
ctx.fill();
ctx.draw();
```

## **入参**

| 参数 | 类型 | **说明** |
| --- | --- | --- |
| x | Number | 矩形左上角的 x 坐标。 |
| y | Number | 矩形左上角的 y 坐标。 |
| width | Number | 矩形路径宽度。 |
| height | Number | 矩形路径高度。 |