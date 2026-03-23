---
title: "设置线条宽度(setLineWidth)"
source: "https://open.dingtalk.com/document/development/canvascontext-setlinewidth"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-setlinewidth_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-setlinewidth_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.setLineWidth**设置线条的宽度。

## **示例代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.beginPath();
ctx.moveTo(20, 20);
ctx.lineTo(250, 10);
ctx.stroke();

ctx.beginPath();
ctx.setLineWidth(10);
ctx.moveTo(20, 35);
ctx.lineTo(250, 30);
ctx.stroke();

ctx.beginPath();
ctx.setLineWidth(20);
ctx.moveTo(20, 50);
ctx.lineTo(250, 55);
ctx.stroke();

ctx.beginPath();
ctx.setLineWidth(25);
ctx.moveTo(20, 80);
```

## **入参**

| 参数 | 类型 | **说明** |
| --- | --- | --- |
| lineWidth | Number | 线条宽度，单位为 px。 |