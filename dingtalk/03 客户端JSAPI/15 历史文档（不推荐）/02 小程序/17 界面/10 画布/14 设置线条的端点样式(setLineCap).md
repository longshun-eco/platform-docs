---
title: "设置线条的端点样式(setLineCap)"
source: "https://open.dingtalk.com/document/development/canvascontext-setlinecap"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-setlinecap_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-setlinecap_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.setLineCap**设置线条的端点样式。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.beginPath();
ctx.moveTo(10, 10);
ctx.lineTo(150, 10);
ctx.stroke();

ctx.beginPath();
ctx.setLineCap('round');
ctx.setLineWidth(20);
ctx.moveTo(20, 70);
ctx.lineTo(250, 80);
ctx.stroke();

ctx.beginPath();
ctx.setLineCap('butt');
ctx.setLineWidth(10);
ctx.moveTo(25, 80);
ctx.lineTo(250, 30);
ctx.stroke();

ctx.beginPath();
```

## 入参

| **参数** | 类型 | **说明** |
| --- | --- | --- |
| lineCap | String | 线条的结束端点样式，范围 'round'、'butt'、'square'。 |