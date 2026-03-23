---
title: "绘制图像(drawImage)"
source: "https://open.dingtalk.com/document/development/canvascontext-drawimage"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-drawimage_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-drawimage_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用CanvasContext.drawImage绘制图像，图像保持原始尺寸。

## **示例****代码**

```javascript
const ctx = dd.createCanvasContext('awesomeCanvas');
ctx.drawImage('https://img.dingding.com/tfs/TB1GvVMj2BNTKJjy0FdXXcPpVXa-520-280.jpg', 2, 2, 250, 80);
ctx.draw();
```

## **入参**

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| imageResource | String | 图片资源, 只支持线上 cdn 地址或离线包地址，线上 cdn 需返回头 `Access-Control-Allow-Origin: *` |
| x | Number | 图像左上角 x 坐标。 |
| y | Number | 图像左上角 y 坐标。 |
| width | Number | 图像宽度。 |
| height | Number | 图像高度。 |