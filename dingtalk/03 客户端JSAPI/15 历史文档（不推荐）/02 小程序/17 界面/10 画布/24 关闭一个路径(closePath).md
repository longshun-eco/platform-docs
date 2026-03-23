---
title: "关闭一个路径(closePath)"
source: "https://open.dingtalk.com/document/development/canvascontext-closepath"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-closepath_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-closepath_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.closePath**关闭一个路径。

**重要**

* 关闭路径会连接起点和终点。
* 如果关闭路径后没有调用 `fill()` 或者 `stroke()` 并开启了新的路径，那之前的路径将不会被渲染。

## **示例代码**

**示例代码一**

```javascript
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.moveTo(20, 20);
ctx.lineTo(150, 20);
ctx.lineTo(150, 150);
ctx.closePath();
ctx.stroke();
ctx.draw();
```

**示例代码二**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.rect(20, 20, 150, 50);
ctx.closePath();

ctx.beginPath();
ctx.rect(20, 50, 150, 40);

ctx.setFillStyle('red');
ctx.fillRect(20, 80, 120, 30);

ctx.rect(20, 150, 150, 40);

ctx.setFillStyle('blue');
ctx.fill();
ctx.draw();
```