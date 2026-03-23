---
title: "填充矩形(fillRect)"
source: "https://open.dingtalk.com/document/development/canvascontext-fillrect"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-fillrect_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-fillrect_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.fillRect**填充矩形。

**重要**

用 `setFillStyle()` 设置矩形的填充色，如果没设置则默认是 `black`。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.fillRect(20, 20, 250, 80);
ctx.setFillStyle('blue');
ctx.draw();
```

## **入参**

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| x | Number | 矩形左上角的 x 坐标。 |
| y | Number | 矩形左上角的 y 坐标。 |
| width | Number | 矩形路径宽度。 |
| height | Number | 矩形路径高度。 |