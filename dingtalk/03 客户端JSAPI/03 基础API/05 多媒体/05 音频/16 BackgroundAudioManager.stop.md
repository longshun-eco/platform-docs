---
title: "BackgroundAudioManager.stop"
source: "https://open.dingtalk.com/document/development/jsapi-background-audio-manager-stop"
category: "客户端JSAPI / 基础API / 多媒体 / 音频"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-background-audio-manager-stop_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-background-audio-manager-stop_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

停止播放背景音乐

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10225) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 否 |
| 第三方企业应用 | 否 |
| 第三方个人应用 | 否 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```javascript
const backgroundAudioManager = dd.getBackgroundAudioManager();

backgroundAudioManager.stop();
```