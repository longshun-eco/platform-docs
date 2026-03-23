---
title: "CanvasContext.stroke"
source: "https://open.dingtalk.com/document/development/jsapi-canvas-context-stroke"
category: "客户端JSAPI / 基础API / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-canvas-context-stroke_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-canvas-context-stroke_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用CanvasContext.stroke，画出当前路径的边框。默认 black。

> stroke() 描绘的的路径是从 beginPath() 开始计算，但是不会将 strokeRect() 包含进去，详情见示例代码二。

示例代码一：

```javascript
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.moveTo(20, 20);
ctx.lineTo(150, 10);
ctx.lineTo(150, 150);
ctx.stroke();
ctx.draw();
```

示例代码二：

```java
const ctx = dd.createCanvasContext('awesomeCanvas');

ctx.rect(10, 10, 100, 30);
ctx.setStrokeStyle('blue');
ctx.stroke();

ctx.beginPath();
ctx.rect(20, 50, 150, 50);

ctx.setStrokeStyle('yellow');
ctx.strokeRect(15, 75, 200, 35);

ctx.rect(20, 200, 150, 30);

ctx.setStrokeStyle('red');
ctx.stroke();
ctx.draw();
```

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10116) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.CanvasContext.stroke({});
```