---
title: "创建线性的渐变色(createLinearGradient)"
source: "https://open.dingtalk.com/document/development/canvascontext-createlineargradient"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-createlineargradient_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-createlineargradient_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.createLinearGradient**创建一个线性的渐变色。

**重要**

需要使用 `addColorStop()` 来指定渐变点，至少需要两个。

## **示例代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

const grd = ctx.createLinearGradient(10, 10, 150, 10);
grd.addColorStop(0, 'yellow');
grd.addColorStop(1, 'blue');

ctx.setFillStyle(grd);
ctx.fillRect(20, 20, 250, 180);
ctx.draw();
```

## 入参

| **参数** | 类型 | 说明 |
| --- | --- | --- |
| x0 | Number | 起点 x 坐标。 |
| x1 | Number | 起点 y 坐标。 |
| y0 | Number | 终点 x 坐标。 |
| y1 | Number | 终点 y 坐标。 |