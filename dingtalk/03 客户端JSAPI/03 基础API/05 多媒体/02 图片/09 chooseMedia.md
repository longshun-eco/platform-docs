---
title: "chooseMedia"
source: "https://open.dingtalk.com/document/development/jsapi-choose-media"
category: "客户端JSAPI / 基础API / 多媒体 / 图片"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-media_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-media_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-16

媒体选择

拍摄或从手机相册中选择图片或视频。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.5.2 | 7.5.2 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11741) |
| 小程序 | 7.5.2 | 7.5.2 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11741) |

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
| count | Number | 否 | 9 | 最多可以选择的文件个数，默认为9。 |
| mediaType | String | 否 | mix | 文件类型：image为只能拍摄图片或从相册选择图片，video为只能拍摄视频或从相册选择视频，mix为可同时选择图片和视频，默认为mix。 |
| sourceType | Array<String> | 否 | ['album', 'camera'] | 图片和视频选择的来源，album为相册，camera为相机拍摄，可以都选择，默认为['album', 'camera']。 |
| maxDuration | Number | 否 | 60 | 拍摄视频最长拍摄时间，单位秒。时间范围为 3s 至 60s 之间。不限制相册。默认为60。 |
| sizeType | String | 否 | original | 是否压缩所选文件：   * original为原图 * compressed为压缩   注意如果选择了压缩，用户在选择后可能会等待较久时间，建议在回调前增加提示等待交互，默认为original |
| camera | String | 否 | back | 仅在 sourceType 为 camera 时生效，使用前置或后置摄像头,可选值为front或者back，默认为back。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| tempFiles | Array<Object> |  | 本地临时文件列表。 |

## **错误码**

| **错误码** | **描述** |
| --- | --- |
| 2 | 参数无效 |
| 3 | 系统异常 |
| -1 | 用户取消 |

## **示例****代码**

### 默认出入参

```javascript
dd.chooseMedia({
  count: 9,
  camera: 'back',
  sizeType: 'original',
  mediaType: 'mix',
  sourceType: ['album', 'camera'],
  maxDuration: 60,
  success: (res) => {
    const { tempFiles } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "tempFiles": [
    {
      "size": 100,
      "width": 1920,
      "height": 1080,
      "duration": 60,
      "fileType": "image",
      "tempFilePath": "https://resource/29663b835195928c6aaf36d8b1ad6.image"
    }
  ]
}
```