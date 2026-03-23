---
title: "顺时针旋转(rotate)"
source: "https://open.dingtalk.com/document/development/canvascontext-rotate"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-rotate_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-rotate_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17以原点为中心（原点可以用translate方法修改），顺时针旋转当前坐标轴。多次调用rotate，旋转的角度会叠加。

## **示例****代码**

```javascript
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.strokeRect(200, 20, 180, 150);
ctx.rotate(30 * Math.PI / 180);
ctx.strokeRect(200, 20, 180, 150);
ctx.rotate(30 * Math.PI / 180);
ctx.strokeRect(200, 20, 180, 150);

ctx.draw();
```

## **入参**

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| rotate | Number | 旋转角度，以弧度计(degrees \* Math.PI/180；degrees 范围为0~360)。 |