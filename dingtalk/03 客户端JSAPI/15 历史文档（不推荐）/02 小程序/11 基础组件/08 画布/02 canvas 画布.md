---
title: "canvas 画布"
source: "https://open.dingtalk.com/document/development/canvas-canvas-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvas-canvas-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvas-canvas-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍画布组件的使用。

## 在线体验

## 属性

| **属性** | **类型** | **说明** |
| --- | --- | --- |
| id | String | 组件唯一标识符。  同一页面中的 `id` 不可重复。如果需要在高 dpr 下取得更细腻的显示，需要先将 `canvas` 用属性设置放大，用样式缩写，例如：  ```  ``` |
| style | String | - |
| class | String | - |
| width | String | **默认值：**300px。 |
| height | String | **默认值：**225px。 |
| disable-scroll | Boolean | 禁止屏幕滚动以及下拉刷新。  **默认值**：false。 |
| onTap | EventHandle | 点击。 |
| onTouchStart | EventHandle | 触摸动作开始。 |
| onTouchMove | EventHandle | 触摸后移动。 |
| onTouchEnd | EventHandle | 触摸动作结束。 |
| onTouchCancel | EventHandle | 触摸动作被打断，如来电提醒，弹窗。 |
| onLongTap | EventHandle | 长按 500ms 之后触发，触发了长按事件后进行移动将不会触发屏幕的滚动。 |

## 示例代码

.axml示例代码：

.js示例代码：

```java
Page({
  onReady() {
    this.point = {
      x: Math.random() * 295,
      y: Math.random() * 295,
      dx: Math.random() * 5,
      dy: Math.random() * 5,
      r: Math.round(Math.random() * 255 | 0),
      g: Math.round(Math.random() * 255 | 0),
          b: Math.round(Math.random() * 255 | 0),
    };

    this.interval = setInterval(() => {this.draw() }, 17);
  },

  draw() {
    var ctx = dd.createCanvasContext('canvas');
    ctx.setFillStyle('#FFF');
    ctx.fillRect(0, 0, 305, 305);

    ctx.beginPath();
```