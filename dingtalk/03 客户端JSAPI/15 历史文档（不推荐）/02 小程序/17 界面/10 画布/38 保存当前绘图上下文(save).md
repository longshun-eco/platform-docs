---
title: "保存当前绘图上下文(save)"
source: "https://open.dingtalk.com/document/development/canvascontext-save"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-save_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-save_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.save**保存当前的绘图上下文。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas')

// save the default fill style
ctx.save();
ctx.setFillStyle('red');
ctx.fillRect(10, 10, 150, 100);

// restore to the previous saved state
ctx.restore();
ctx.fillRect(50, 50, 150, 100);

ctx.draw();
```