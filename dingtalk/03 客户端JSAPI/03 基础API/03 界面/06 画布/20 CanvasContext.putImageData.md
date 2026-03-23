---
title: "CanvasContext.putImageData"
source: "https://open.dingtalk.com/document/development/jsapi-canvas-context-put-image-data"
category: "客户端JSAPI / 基础API / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-canvas-context-put-image-data_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-canvas-context-put-image-data_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用CanvasContext.putImageData，将像素数据绘制到画布。

使用 dd.canIUse('createCanvasContext.putImageData') 进行可用性判断。

```java
const data = new Uint8ClampedArray([255, 0, 0, 1])
const ctx = dd.createCanvasContext('canvas')

ctx.putImageData({
    x: 0,
    y: 0,
    width: 1,
    height: 1,
    data: data,
    success(res) {}
})
```

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10098) |

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
| data | Array<Object> | 是 | data | 图像像素点数据，一维数组，每四项表示一个像素点的 rgba。 |
| x | Number | 是 | 0 | 源图像数据在目标画布中的位置偏移量（x 轴方向的偏移量）。 |
| y | Number | 是 | 0 | 源图像数据在目标画布中的位置偏移量（y 轴方向的偏移量）。 |
| width | Number | 是 | 10 | 源图像数据矩形区域的宽度 。 |
| height | Number | 是 | 10 | 源图像数据矩形区域的高度 。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.CanvasContext.putImageData({
  x: 0,
  y: 0,
  data: data,
  width: 1,
  height: 10,
});
```