---
title: "onRecordEnd"
source: "https://open.dingtalk.com/document/development/jsapi-on-record-end"
category: "客户端JSAPI / 基础API / 多媒体 / 录音"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-on-record-end_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-on-record-end_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用onRecordEnd，监听录音自动停止。

当语音录制时间超过60秒时，钉钉会自动停止语音录制，同时将录制的语音上传到服务端，返回音频资源的MediaID。推荐在调用startRecord前设置监听录音自动停止的回调。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11680) |
| 小程序 | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

调用[dd.config](https://open.dingtalk.com/document/orgapp/jsapi-authentication)完成鉴权后使用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| mediaId | String | @media\*\*\* | 停止播放音频MediaId。 |
| duration | String | 60 | 返回音频的时长，单位：秒。 |

## **示例****代码**

### 默认出入参

```javascript
dd.onRecordEnd({
  success: (res) => {
    const { mediaId, duration } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "mediaId": "@media***", "duration": "60" }
```