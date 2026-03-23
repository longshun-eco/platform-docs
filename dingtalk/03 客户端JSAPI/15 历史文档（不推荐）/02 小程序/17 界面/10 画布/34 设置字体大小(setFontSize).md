---
title: "设置字体大小(setFontSize)"
source: "https://open.dingtalk.com/document/development/canvascontext-setfontsize"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-setfontsize_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-setfontsize_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.setFontSize**设置字体大小。

## **示例****代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas')；

ctx.setFontSize(14)；
ctx.fillText('14', 20, 20)；；；
ctx.setFontSize(22)
ctx.fillText('22', 40, 40)
ctx.setFontSize(30)；
ctx.fillText('30', 60, 60)；
ctx.setFontSize(38)；
ctx.fillText('38', 90, 90)；

ctx.draw()；
```

## **入参**

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| fontSize | Number | 字号。 |