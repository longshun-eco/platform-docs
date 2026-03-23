---
title: "CanvasContext.beginPath"
source: "https://open.dingtalk.com/document/development/jsapi-canvas-context-begin-path"
category: "客户端JSAPI / 基础API / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-canvas-context-begin-path_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-canvas-context-begin-path_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用CanvasContext.beginPath开始创建一个路径，需要调用 fill 或者 stroke 才会使用路径进行填充或描边。

> 在最开始的时候相当于调用了一次 beginPath()。
> 同一个路径内的多次setFillStyle()、setStrokeStyle()、setLineWidth()等设置，以最后一次设置为准。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10083) |

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

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| ![[development-jsapi-canvas-context-begin-path_O1CN019V5Laa1JL54vlyQ2F_!!6000000001011-2-tps-360-360.png]] 暂无内容 | | | |

## **示例****代码**

### 默认出入参

```
dd.CanvasContext.beginPath();
```

`success`返回对象示例：

```json
{}
```