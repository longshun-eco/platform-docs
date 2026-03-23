---
title: "CanvasContext.bezierCurveTo"
source: "https://open.dingtalk.com/document/development/jsapi-canvas-context-bezier-curve-to"
category: "客户端JSAPI / 基础API / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-canvas-context-bezier-curve-to_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-canvas-context-bezier-curve-to_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用CanvasContext.bezierCurveTo，创建三次方贝塞尔曲线路径。曲线的起始点为路径中前一个点。

针对 moveTo(30, 30)bezierCurveTo(30, 150, 250, 150, 180, 20) 的三个关键坐标如下：

红色：起始点(20, 20)

蓝色：两个控制点(20, 150) (250, 150)

绿色：终止点(180, 20)

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10084) |

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
| x | Number | 是 | 180 | 结束点 x 坐标。 |
| y | Number | 是 | 20 | 结束点 y 坐标。 |
| cp1x | Number | 是 | 30 | 第一个贝塞尔控制点 x 坐标。 |
| cp1y | Number | 是 | 150 | 第一个贝塞尔控制点 y 坐标。 |
| cp2x | Number | 是 | 250 | 第二个贝塞尔控制点 x 坐标。 |
| cp2y | Number | 是 | 150 | 第二个贝塞尔控制点 y 坐标。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| ![[development-jsapi-canvas-context-bezier-curve-to_O1CN019V5Laa1JL54vlyQ2F_!!6000000001011-2-tps-360-360.png]] 暂无内容 | | | |

## **示例****代码**

### 默认出入参

```
dd.CanvasContext.bezierCurveTo(180, 20, 30, 150, 250, 150);
```

`success`返回对象示例：

```json
{}
```