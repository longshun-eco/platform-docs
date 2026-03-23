---
title: "创建二次贝塞尔曲线路径(quadraticCurveTo)"
source: "https://open.dingtalk.com/document/development/canvascontext-quadraticcurveto"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-quadraticcurveto_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-quadraticcurveto_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.quadraticCurveTo**创建二次贝塞尔曲线路径。曲线的起始点为路径中前一个点。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.beginPath();
ctx.arc(30, 30, 2, 0, 2 * Math.PI);
ctx.setFillStyle('red');
ctx.fill();

ctx.beginPath();
ctx.arc(250, 20, 2, 0, 2 * Math.PI);
ctx.setFillStyle('blue');
ctx.fill();

ctx.beginPath();
ctx.arc(30, 200, 2, 0, 2 * Math.PI);
ctx.setFillStyle('green');
ctx.fill();

ctx.setFillStyle('black');
ctx.setFontSize(12);

ctx.beginPath();
```

针对 `moveTo(30, 30)``quadraticCurveTo(30, 150, 250, 25)` 的三个关键坐标如下：

* 红色：起始点(30, 30)
* 蓝色：控制点(30, 150)
* 绿色：终止点(250, 25)

## **入参**

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| cpx | Number | 贝塞尔控制点 x 坐标。 |
| cpy | Number | 贝塞尔控制点 y 坐标。 |
| x | Number | 结束点 x 坐标。 |
| y | Number | 结束点 y坐标。 |