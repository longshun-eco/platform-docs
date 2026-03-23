---
title: "RecorderManager.onframerecorded"
source: "https://open.dingtalk.com/document/development/jsapi-recorder-manager-on-frame-recorded"
category: "客户端JSAPI / 基础API / 多媒体 / 录音"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-recorder-manager-on-frame-recorded_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-recorder-manager-on-frame-recorded_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

监听已录制完制定帧大小的文件事件。

> 如果设置了 frameSize，则会回调此事件。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 7.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11484) |

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
| type | String | onframerecorded | 类型。 |
| frameBuffer | String | Base64格式数据 | 录音分片数据。 |
| isLastFrame | Boolean | true或者false | 当前帧是否正常录音结束前的最后一帧。 |

## **示例****代码**

### 默认出入参

```javascript
const recorderManager = dd.getRecorderManager();

recorderManager.onframerecorded = (res) => {
  console.log('onFrameRecorded', JSON.stringify(res));
  console.log('onFrameRecorded arraybuffer', JSON.stringify(res.frameBuffer));
};
recorderManager.start({ duration: 10, frameSize: 50 });
```

`success`返回对象示例：

```json
{
  "type": "onframerecorded",
  "frameBuffer": "Base64格式数据",
  "isLastFrame": true
}
```