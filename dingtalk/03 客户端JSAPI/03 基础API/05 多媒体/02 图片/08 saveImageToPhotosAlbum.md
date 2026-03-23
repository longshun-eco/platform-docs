---
title: "saveImageToPhotosAlbum"
source: "https://open.dingtalk.com/document/development/jsapi-save-image-to-photos-album"
category: "客户端JSAPI / 基础API / 多媒体 / 图片"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-save-image-to-photos-album_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-save-image-to-photos-album_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

保存图片到系统相册

保存图片到系统相册，仅支持本地图片。保存结果会有Toast提示。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.0.0 | 7.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11752) |
| 小程序 | 7.0.0 | 7.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11752) |

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
| filePath | String | 是 | /data/path/to/image | 图片文件路径，仅支持本地虚拟路径。例如: https://resource/xxxx.image |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **错误码**

| **错误码** | **描述** |
| --- | --- |
| 2 | 参数无效 |
| 3 | 系统异常 |
| 17 | 保存失败 |

## **示例****代码**

### 默认Demo标题

```
dd.saveImageToPhotosAlbum({
  filePath: '/data/path/to/image',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```