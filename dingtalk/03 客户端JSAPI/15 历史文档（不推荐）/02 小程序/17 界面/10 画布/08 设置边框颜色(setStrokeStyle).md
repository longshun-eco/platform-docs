---
title: "设置边框颜色(setStrokeStyle)"
source: "https://open.dingtalk.com/document/development/canvascontext-setstrokestyle"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-setstrokestyle_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-setstrokestyle_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.setStrokeStyle**设置边框颜色。

**说明**

如果没有设置 `strokeStyle`，则默认颜色为 `black`。

## **示例代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.setStrokeStyle('blue');
ctx.strokeRect(50, 50, 100, 175);
ctx.draw();
```

## **入参说明**

| **参数** | **类型** | **说明** |
| --- | --- | --- |
| color | String | 颜色，如：blue，Hex格式：#000000。 |