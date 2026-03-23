---
title: "画出当前路径的边框(stroke)"
source: "https://open.dingtalk.com/document/development/canvascontext-stroke"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-stroke_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-stroke_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext****.stroke**画出当前路径的边框。默认 black。

**重要**

`stroke()` 描绘的的路径是从 `beginPath()` 开始计算，但是不会将 `strokeRect()` 包含进去，详情见**示例代码二**。

## **示例代码**

**示例代码一**

```javascript
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.moveTo(20, 20);
ctx.lineTo(150, 10);
ctx.lineTo(150, 150);
ctx.stroke();
ctx.draw();
```

**示例代码二**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.rect(10, 10, 100, 30);
ctx.setStrokeStyle('blue');
ctx.stroke();

ctx.beginPath();
ctx.rect(20, 50, 150, 50);

ctx.setStrokeStyle('yellow');
ctx.strokeRect(15, 75, 200, 35);

ctx.rect(20, 200, 150, 30);

ctx.setStrokeStyle('red');
ctx.stroke();
ctx.draw();
```