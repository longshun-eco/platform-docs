---
title: "恢复绘图上下文(restore)"
source: "https://open.dingtalk.com/document/development/canvascontext-restore"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-restore_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-restore_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.restore**恢复之前保存的绘图上下文。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.save();
ctx.setFillStyle('red');
ctx.fillRect(20, 20, 250, 80);

ctx.restore();
ctx.fillRect(60, 60, 155, 130);

ctx.draw();
```