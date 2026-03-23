---
title: "移动路径(moveTo)"
source: "https://open.dingtalk.com/document/development/canvascontext-moveto"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-moveto_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-moveto_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.moveTo**将路径移动到画布中的指定点，不创建线条。

**重要**

用 `stroke()` 方法来画线条。

## **示例****代码**

```javascript
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.moveTo(20, 20);
ctx.lineTo(150, 15);

ctx.moveTo(20, 55);
ctx.lineTo(120, 60);
ctx.stroke();
ctx.draw();
```

## **入参**

| **参数** | 类型 | 说明 |
| --- | --- | --- |
| x | Number | 目标位置 x 坐标。 |
| y | Number | 目标位置 y 坐标 。 |