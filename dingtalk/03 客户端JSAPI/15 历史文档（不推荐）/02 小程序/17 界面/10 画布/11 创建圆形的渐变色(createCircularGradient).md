---
title: "创建圆形的渐变色(createCircularGradient)"
source: "https://open.dingtalk.com/document/development/canvascontext-createcirculargradient"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-createcirculargradient_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-createcirculargradient_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.createCircularGradient**创建一个圆形的渐变色。

**重要**

* 起点在圆心，终点在圆环。
* 需要使用 `addColorStop()` 来指定渐变点，至少需要两个。

## **示例代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

const grd = ctx.createCircularGradient(90, 60, 60);
grd.addColorStop(0, 'blue');
grd.addColorStop(1, 'red');

ctx.setFillStyle(grd);
ctx.fillRect(20, 20, 250, 180);
ctx.draw();
```

## **入参**

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| x | Number | 圆心 x 坐标。 |
| y | Number | 圆心 y坐标。 |
| r | Number | 圆半径。 |