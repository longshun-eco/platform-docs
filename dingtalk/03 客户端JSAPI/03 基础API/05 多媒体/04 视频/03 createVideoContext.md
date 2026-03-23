---
title: "createVideoContext"
source: "https://open.dingtalk.com/document/development/jsapi-create-video-context"
category: "客户端JSAPI / 基础API / 多媒体 / 视频"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-create-video-context_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-create-video-context_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用dd.createVideoContext(videoId)创建并返回一个 video上下文对象videoContext，videoId 为 video 组件的 id 属性设置的值。

.axml示例代码：

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

### videoContext方法

| 方法名 | 参数 | 类型 | 说明 |
| --- | --- | --- | --- |
| play | - | - | 播放。 |
| pause | - | - | 暂停。 |
| stop | - | - | 终止。 |
| seek | position | Number | 定位，单位为秒（s）。 |
| mute | ison | Boolean | 切换静音状态。 |
| requestFullScreen | direction | Number | 进入全屏。0：正常竖屏。90：横屏。-90：反向横屏。 |
| exitFullScreen | - | - | 退出全屏。 |
| snapshot | quality | String | 截图，可选值 raw compressed。 |
| playbackRate | rate | Number | 设置倍速播放（0.5 <= rate <= 2.0）。 |

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10200) |

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
| id | String | 是 | videoId | videoId。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.createVideoContext('video');
```