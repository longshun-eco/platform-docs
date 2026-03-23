---
title: "设置为剪切路径(clip)"
source: "https://open.dingtalk.com/document/development/canvascontext-clip"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-canvascontext-clip_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-canvascontext-clip_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**CanvasContext.clip**将当前创建的路径设置为当前剪切路径。

## **示例****代码**

```javascript
const ctx = dd.createCanvasContext('awesomeCanvas')
dd.downloadFile({
  url: 'https://gw.dingding.com/zos/skylark-tools/public/files/dda114e320567e1d304790287d75a029.png',
  success: function(res) {
    ctx.save();
    ctx.beginPath();
    ctx.arc(50, 50, 25, 0, 2*Math.PI);
    ctx.clip();
    ctx.drawImage(res.tempFilePath, 25, 25);
    ctx.restore();
    ctx.draw();
  }
})
```