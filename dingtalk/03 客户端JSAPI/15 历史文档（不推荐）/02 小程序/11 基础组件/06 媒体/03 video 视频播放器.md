---
title: "video 视频播放器"
source: "https://open.dingtalk.com/document/development/mini-app-video-player-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 媒体"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-video-player-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-video-player-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍视频播放器组件的介绍。

开发者可通过 video 组件播放视频。

**重要**

video 组件的 **enableNative** 属性，必须设置成 **true**。原因是有少量小程序还在使用旧版本视频播放器。本文介绍的功能，只针对新版 Native 播放器。

## 属性

|  |  |  |
| --- | --- | --- |
| **属性** | **类型** | **说明** |
| class | String | class 名称。 |
| style | String | 内联样式。 |
| id | String | video组件id。 |
| src | String | 视频地址。仅支持网络视频地址。 |
| autoplay | Boolean | 自动播放。  **默认值**：false。 |
| controls | Boolean | 显示控制器。  **默认值**：true。 |
| loop | Boolean | 循环。  **默认值**：false。 |
| muted | Boolean | 静音。  **默认值**：false。 |
| objectFit | String | 填充形式：   * **contain**（默认值）：包含 * **fill**：填充 * **cover**：覆盖 |
| enableNative | Boolean | 是否使用native版播放器。  **默认值**：false。 |
| onPlay | Function | 播放开始时的回调。 |
| onPause | Function | 播放暂停时的回调。 |
| onEnded | Function | 播放结束时的回调。 |
| onTimeUpdate | Function | 播放进度变化时的回调。event.detail = {currentTime, duration}，单位毫秒。 |
| onFullScreenChange | Function | 全屏/退出全屏时的回调。event.detail = {fullScreen}。 |
| onWaiting | Function | 视频缓冲时的回调。 |
| onError | Function | 视频播放出错时的回调。 |

## 支持的格式

|  |  |
| --- | --- |
| **类型** | **格式** |
| 网络协议 | http、https、rtmp、rtp、artp  **说明**  rtmp协议，Android端不支持。 |
| 媒体文件格式 | mp4、flv、m3u8、mpegts |
| 视频编码类型 | H.264、H.265 |
| 音频编码类型 | AAC(HE、HE-v2)、PCM |
| NALU header格式 | Annex-B、MPEG-4（avcc、hvcc） |

## **示例代码**

.axml示例代码：

```
  Video视频

      [](your video url)
```