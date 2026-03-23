---
title: "文本对齐方式(setTextAlign)"
source: "https://open.dingtalk.com/document/development/canvascontext-settextalign"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-settextalign_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-settextalign_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17**CanvasContext.setTextAlign**是 Canvas 2D API 描述绘制文本时，文本的对齐方式。

**重要**

该对齐是基于CanvasRenderingContext2D.fillText 方法的x的值。如果 textAlign="center"，那么该文本将画在 x-50%\*width。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.setTextAlign("left");
ctx.fillText("Hello world", 0, 100);
```

## **入参**

| **参数** | **类型** | **说明** |
| --- | --- | --- |
| textAlign | String | 枚举 "left" "right" "center" "start" "end"。 |