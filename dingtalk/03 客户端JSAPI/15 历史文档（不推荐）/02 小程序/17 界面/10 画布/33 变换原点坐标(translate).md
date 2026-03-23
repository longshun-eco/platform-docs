---
title: "变换原点坐标(translate)"
source: "https://open.dingtalk.com/document/development/canvascontext-translate"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-translate_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-translate_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用CanvasContext.translate对当前坐标系的原点(0, 0)进行变换，默认的坐标系原点为页面左上角。

## **示例****代码**

```javascript
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.strokeRect(20, 20, 250, 80);
ctx.translate(30, 30);
ctx.strokeRect(20, 20, 250, 80);
ctx.translate(30, 30);
ctx.strokeRect(20, 20, 250, 80);

ctx.draw();
```

## **入参**

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| x | Number | 水平坐标平移量。 |
| y | Number | 竖直坐标平移量。 |