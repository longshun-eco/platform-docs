---
title: "设置线条的交点样式(setLineJoin)"
source: "https://open.dingtalk.com/document/development/canvascontext-setlinejoin"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-setlinejoin_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-setlinejoin_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.setLineJoin**设置线条的交点样式。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.beginPath();
ctx.moveTo(20, 30);
ctx.lineTo(150, 70);
ctx.lineTo(20, 100);
ctx.stroke();

ctx.beginPath();
ctx.setLineJoin('round');
ctx.setLineWidth(20);
ctx.moveTo(100, 20);
ctx.lineTo(280, 80);
ctx.lineTo(100, 100);
ctx.stroke();

ctx.beginPath();
ctx.setLineJoin('bevel');
ctx.setLineWidth(20);
ctx.moveTo(60, 25);
ctx.lineTo(180, 80);
ctx.lineTo(90, 100);
```

## **入参**

| 参数 | 类型 | **说明** |
| --- | --- | --- |
| lineJoin | String | 线条的结束交点样式，范围 'round'、'bevel'、'miter'。 |