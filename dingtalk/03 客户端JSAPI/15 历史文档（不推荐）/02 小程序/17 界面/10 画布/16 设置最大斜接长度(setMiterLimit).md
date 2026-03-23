---
title: "设置最大斜接长度(setMiterLimit)"
source: "https://open.dingtalk.com/document/development/canvascontext-setmiterlimit"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-setmiterlimit_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-setmiterlimit_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.setMiterLimit**设置最大斜接长度，斜接长度指的是在两条线交汇处内角和外角之间的距离。

当 `setLineJoin()` 为 miter 时才有效。超过最大倾斜长度的，连接处将以 lineJoin 为 bevel 来显示。

## **示例代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.beginPath();
ctx.setLineWidth(15);
ctx.setLineJoin('miter');
ctx.setMiterLimit(1);
ctx.moveTo(10, 10);
ctx.lineTo(100, 50);
ctx.lineTo(10, 90);
ctx.stroke();

ctx.beginPath();
ctx.setLineWidth(15);
ctx.setLineJoin('miter');
ctx.setMiterLimit(2);
ctx.moveTo(50, 10);
ctx.lineTo(140, 50);
ctx.lineTo(50, 90);
ctx.stroke();

ctx.beginPath();
ctx.setLineWidth(15);
```

## **入参**

| 参数 | 类型 | **说明** |
| --- | --- | --- |
| miterLimit | Number | 最大斜接长度。 |