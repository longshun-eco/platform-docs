---
title: "创建canvas"
source: "https://open.dingtalk.com/document/development/create-a-canvas"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-create-a-canvas_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-create-a-canvas_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.createCanvasContext(canvasId)** 创建canvas绘图上下文。

**重要**

该绘图上下文只作用于对应 `canvasId` 的 `<canvas/>。`

## **扫码体验**

![[development-create-a-canvas_p172097.png]]

## **入参**

|  |  |  |
| --- | --- | --- |
| **参数** | **类型** | **说明** |
| canvasId | String | 定义在`<canvas/>`上的 id。 |

## **返回值**

返回值为[CanvasContext概览](/document/orgapp/overview-of-canvascontext)。