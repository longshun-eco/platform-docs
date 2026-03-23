---
title: "设置阴影样式(setShadow)"
source: "https://open.dingtalk.com/document/development/canvascontext-setshadow"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-setshadow_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-setshadow_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.setShadow**设置阴影样式。

**说明**

如果没有设置，`offsetX` 的默认值为 0， `offsetY` 的默认值为 0， `blur` 的默认值为 0，`color` 的默认值为 `black`。

## **示例代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.setStrokeStyle('blue');
ctx.strokeRect(50, 50, 100, 175);
ctx.draw();
```

## 入参

| **参数** | **类型** | **说明** |
| --- | --- | --- |
| offsetX | Number | 阴影相对于形状水平方向的偏移。 |
| offsetY | Number | 阴影相对于形状竖直方向的偏移。 |
| blur | Number | 阴影的模糊级别，值越大越模糊，范围 0~100。 |
| color | String | 阴影颜色。 |