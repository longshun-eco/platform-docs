---
title: "绘制被填充的文本(fillText)"
source: "https://open.dingtalk.com/document/development/canvascontext-filltext"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-filltext_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-filltext_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.fillText**在画布上绘制被填充的文本。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.setFontSize(42);
ctx.fillText('Hello', 30, 30);
ctx.fillText('Dingtalk', 200, 200);

ctx.draw();
```

## **入参**

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| text | String | 文本。 |
| x | Number | 绘制文本的左上角 x 坐标。 |
| y | Number | 绘制文本的左上角 y 坐标。 |