---
title: "chooseVideo"
source: "https://open.dingtalk.com/document/development/jsapi-choose-video"
category: "客户端JSAPI / 基础API / 多媒体 / 视频"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-video_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-video_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用chooseVideo，拍摄视频或从手机相册中选视频。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 7.0.55 | 7.0.55 | 不支持 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10208) |

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
| compressed | Boolean | 否 | false | 是否对所选取视频进行压缩，默认为false。 |
| sourceType | Array<String> | 否 | ['album','camera'] | 视频来源。**默认值**：['album','camera']。桌面端不支持该参数。 |
| maxDuration | String | 否 | 50 | 最长视频拍摄时间，单位为秒，**默认值**：10。取值范围：Android：5-300 iOS：15-300 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| size | Number | 12334 | 视频数据大小，单位字节。 |
| width | Number | 200 | 视频宽度（桌面端不支持该字段）。 |
| filePath | String | https://resource/apml31fc26337c885be15b4fd1c0abefee8f.video | 视频临时文件路径。 |
| duration | Number | 40 | 视频时间长度，单位秒（桌面端不支持该字段）。 |
| height | Number | 200 | 视频高度（桌面端不支持该字段）。 |

## **示例****代码**

### 默认出入参

```
dd.chooseVideo({
  sourceType: ['album', 'camera'],
  maxDuration: 60,
  compressed: true,
  success: (res) => {
    console.log(res);
  },
  fail: (err) => {
    console.log(err);
  },
});
```

`success`返回对象示例：

```json
{
  "size": 12334,
  "width": 200,
  "height": 200,
  "duration": 40,
  "filePath": "https://resource/apml31fc26337c885be15b4fd1c0abefee8f.video"
}
```