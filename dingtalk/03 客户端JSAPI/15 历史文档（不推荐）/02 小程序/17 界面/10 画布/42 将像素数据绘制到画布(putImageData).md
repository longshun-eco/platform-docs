---
title: "将像素数据绘制到画布(putImageData)"
source: "https://open.dingtalk.com/document/development/canvascontext-putimagedata"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-putimagedata_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-putimagedata_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用CanvasContext.putImageData将像素数据绘制到画布。

**重要**

使用 dd.canIUse('createCanvasContext.putImageData') 进行可用性判断。

## **示例****代码**

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

## **入参**

| 参数 | 类型 | 是否必填 | 说明 |
| --- | --- | --- | --- |
| data | Uint8ClampedArray | 是 | 图像像素点数据，一维数组，每四项表示一个像素点的 rgba。 |
| x | Number | 是 | 源图像数据在目标画布中的位置偏移量（x 轴方向的偏移量）。 |
| y | Number | 是 | 源图像数据在目标画布中的位置偏移量（y 轴方向的偏移量）。 |
| width | Number | 是 | 源图像数据矩形区域的宽度 。 |
| height | Number | 是 | 源图像数据矩形区域的高度。 |
| success | Function | 否 | 成功回调。 |
| fail | Function | 否 | 失败回调。 |
| complete | Function | 否 | 完成回调。 |