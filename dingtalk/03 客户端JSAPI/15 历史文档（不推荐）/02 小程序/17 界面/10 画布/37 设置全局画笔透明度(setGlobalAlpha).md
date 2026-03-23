---
title: "设置全局画笔透明度(setGlobalAlpha)"
source: "https://open.dingtalk.com/document/development/canvascontext-setglobalalpha"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-setglobalalpha_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-setglobalalpha_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.setGlobalAlpha**设置全局画笔透明度。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.setFillStyle('yellow');
ctx.fillRect(10, 10, 150, 100);
ctx.setGlobalAlpha(0.2);
ctx.setFillStyle('blue');
ctx.fillRect(50, 50, 150, 100);
ctx.setFillStyle('red');
ctx.fillRect(100, 100, 150, 100);

ctx.draw();
```

## **入参**

| 参数 | 类型 | 范围 | 说明 |
| --- | --- | --- | --- |
| alpha | Number | 0~1 | 透明度。  **0**：完全透明  **1**：不透明 |