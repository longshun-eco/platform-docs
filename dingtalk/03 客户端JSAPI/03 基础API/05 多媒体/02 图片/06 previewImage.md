---
title: "previewImage"
source: "https://open.dingtalk.com/document/development/jsapi-preview-image"
category: "客户端JSAPI / 基础API / 多媒体 / 图片"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-preview-image_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-preview-image_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用previewImage，预览图片。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10197) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10197) |

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
| urls | Array<String> | 是 | ['https://gw.alicdn.com/imgextra/i3/O1CN01Eg6xCm1nnsXZCnkP4\_!!6000000005135-2-tps-200-200.png', 'https://gw.alicdn.com/imgextra/i1/O1CN01ug6HAx1eAe42KAHSF\_!!6000000003831-2-tps-200-200.png'] | 要预览的图片链接列表。 |
| current | Number | 否 | 1 | 当前显示图片索引，默认值：0。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.previewImage({
  urls: [
    'https://gw.alicdn.com/imgextra/i3/O1CN01Eg6xCm1nnsXZCnkP4_!!6000000005135-2-tps-200-200.png',
    'https://gw.alicdn.com/imgextra/i1/O1CN01ug6HAx1eAe42KAHSF_!!6000000003831-2-tps-200-200.png',
  ],
  current: 1,
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```