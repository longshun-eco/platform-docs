---
title: "缩放(scale)"
source: "https://open.dingtalk.com/document/development/canvascontext-scale"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-scale_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-scale_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17在调用scale方法后，之后创建的路径其横纵坐标会被缩放。多次调用scale，倍数会相乘。

## **示例****代码**

```javascript
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.strokeRect(15, 15, 30, 25);
ctx.scale(3, 3);
ctx.strokeRect(15, 15, 30, 25);
ctx.scale(3, 3);
ctx.strokeRect(15, 15, 30, 25);

ctx.draw();
```

## **入参**

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| scaleWidth | Number | 横坐标缩放倍数 (1 = 100%，0.5 = 50%，2 = 200%)。 |
| scaleHeight | Number | 纵坐标轴缩放倍数 (1 = 100%，0.5 = 50%，2 = 200%)。 |