---
title: "创建video对象"
source: "https://open.dingtalk.com/document/development/dd-createvideocontext-videoid"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 多媒体 / 视频"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-createvideocontext-videoid_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-createvideocontext-videoid_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.createVideoContext(videoId)**创建并返回一个 video上下文对象videoContext，videoId 为 video 组件的 id 属性设置的值。

## 使用方法

```
this.videoCtx = dd.createVideoContext('video');
```

## **代码示例**

**.**axml示例代码：

```
[ ]({{videoUrl}})
```

.js示例代码：

```javascript
Page({
  data: {
    videoUrl:'xxx'
  },
  onTimeUpdate(e) {
    console.log('onTimeUpdate: currentTime' + e.detail.currentTime)
  },
  pause() {
    let ctx = dd.createVideoContext('v');
    ctx.pause();
  },
  seek30s() {
    let ctx = dd.createVideoContext('v');
    ctx.seek(30);
  }
});
```

## **videoContext方法**

| 方法名 | 参数 | 类型 | 说明 |
| --- | --- | --- | --- |
| play | - | - | 播放。 |
| pause | - | - | 暂停。 |
| stop | - | - | 终止。 |
| seek | position | Number | 定位，单位为秒（s）。 |
| requestFullScreen | direction | Number | 进入全屏。 |
| exitFullScreen | - | - | 退出全屏。 |
| snapshot | quality | String | 截图，可选值 raw compressed。 |

**snapshot 详细说明**

**兼容性：**

**请使用 dd.canIUse('**createVideoContext**.**return.snapshot**') 进行兼容性判断**

且仅支持 native video，即 video 标签有属性 enableNative="{{true}}"。

H5 video 将返回

```json
{
    error: -1,
    errorMessage: 'not support for web video component'
}
```

**定义：**

```
interface IResult {
    width: number; // 图片宽度
  height: number; // 图片高度
  tempImagePath: string; // 本地图片虚拟路径
}

interface ISnapshot {
  (quality: 'raw' | 'compressed'): Promise
}
```

## 支持的格式

| **类型** | **格式** |
| --- | --- |
| 网络协议 | http、https、rtmp、rtp、artp、tcp、udp、file |
| 媒体文件格式 | mp4、flv、m3u8、mpegts |
| 视频编码类型 | H.264、H.265 |
| 音频编码类型 | AAC(HE、HE-v2)、PCM |
| NALU header格式 | Annex-B、MPEG-4（avcc、hvcc） |