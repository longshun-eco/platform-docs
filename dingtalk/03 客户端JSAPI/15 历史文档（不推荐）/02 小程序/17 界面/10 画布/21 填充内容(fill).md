---
title: "填充内容(fill)"
source: "https://open.dingtalk.com/document/development/canvascontext-fill"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-fill_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-fill_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.fill**对当前路径中的内容进行填充。默认的填充色为黑色。

**重要**

* 如果当前路径没有闭合，`fill()` 方法会将起点和终点进行连接，然后填充，详情见**示例代码一**。
* `fill()` 填充的的路径是从 `beginPath()` 开始计算，但是不会将 `fillRect()` 包含进去，详情见**示例代码二**。

## **示例代码**

**示例代码一**

```javascript
const ctx = dd.createCanvasContext('awesomeCanvas')
ctx.moveTo(20, 20)
ctx.lineTo(200, 20)
ctx.lineTo(200, 200)
ctx.fill()
ctx.draw(
)
```

**示例代码二**

```java
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.rect(20, 20, 110, 40);
ctx.setFillStyle('blue');
ctx.fill();

ctx.beginPath();
ctx.rect(20, 30, 150, 40);

ctx.setFillStyle('yellow');
ctx.fillRect(20, 80, 150, 40);

ctx.rect(20, 150, 150, 40);

ctx.setFillStyle('red');
ctx.fill();
ctx.draw();
```