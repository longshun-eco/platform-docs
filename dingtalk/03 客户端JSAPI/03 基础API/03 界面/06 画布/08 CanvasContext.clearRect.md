---
title: "CanvasContext.clearRect"
source: "https://open.dingtalk.com/document/development/jsapi-canvas-context-clear-rect"
category: "客户端JSAPI / 基础API / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-canvas-context-clear-rect_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-canvas-context-clear-rect_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用CanvasContext.clearRect，清除画布上在该矩形区域内的内容。

> clearRect 并非画一个白色的矩形在地址区域，而是清空，为了有直观感受，可以对 canvas 加一层背景色。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10085) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| x | Number | 是 | 0 | 矩形左上角的 x 坐标。 |
| y | Number | 是 | 0 | 矩形左上角的 y 坐标。 |
| width | Number | 是 | 10 | 矩形宽度。 |
| height | Number | 是 | 20 | 矩形高度。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.setFillStyle('blue');
ctx.fillRect(250, 10, 250, 200);
ctx.setFillStyle('yellow');
ctx.fillRect(0, 0, 150, 200);
ctx.clearRect(10, 10, 150, 75);
ctx.draw();
```