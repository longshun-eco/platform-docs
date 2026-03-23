---
title: "文本基线（setTextBaseline）"
source: "https://open.dingtalk.com/document/development/canvascontext-settextbaseline"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-settextbaseline_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-settextbaseline_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17**textBaseline**是 Canvas 2D API 描述绘制文本时，当前文本基线的属性。

## **示例代码**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.setTextBaseline("top");
ctx.fillText("Hello world", 0, 100);
```

## **入参**

| **参数** | **类型** | **说明** |
| --- | --- | --- |
| textBaseline | String | 枚举 "top" "hanging" "middle""alphabetic" "ideographic" "bottom"。 |