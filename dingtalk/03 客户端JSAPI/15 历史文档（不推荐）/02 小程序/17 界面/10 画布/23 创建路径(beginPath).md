---
title: "创建路径(beginPath)"
source: "https://open.dingtalk.com/document/development/canvascontext-beginpath"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-beginpath_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-beginpath_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContex****t.beginPath**开始创建一个路径，需要调用 fill 或者 stroke 才会使用路径进行填充或描边。

**重要**

* 在最开始的时候相当于调用了一次 `beginPath()`。
* 同一个路径内的多次`setFillStyle()`、`setStrokeStyle()`、`setLineWidth()`等设置，以最后一次设置为准。

## **示例代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.rect(20, 20, 150, 50);
ctx.setFillStyle('blue');
ctx.fill();

ctx.beginPath();
ctx.rect(20, 50, 150, 40);

ctx.setFillStyle('yellow');
ctx.fillRect(20, 170, 150, 40);

ctx.rect(10, 100, 100, 30);

ctx.setFillStyle('red');
ctx.fill();
ctx.draw();
```