---
title: "share"
source: "https://open.dingtalk.com/document/development/jsapi-share"
category: "客户端JSAPI / 基础API / 分享"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-share_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-share_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用share，实现分享功能。

![[development-jsapi-share_p177828.png]]

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11673) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11673) |

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
| url | String | 否 | https://www.dingtalk.com | url地址。 |
| type | Number | 是 | 0 | 分享类型：   * 0：全部组件默认 * 1：只能分享到钉钉 * 2：不能分享，只有刷新按钮 |
| title | String | 是 | 钉钉官网 | 分享标题。 |
| content | String | 否 | 钉钉官网 | 分享内容。 |
| image | String | 否 | https://img.alicdn.com/imgextra/i1/O1CN01SNHEw41ysQFPN5Ql6\_!!6000000006634-55-tps-176-31.svg | 分享的图片url地址。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.share({
  url: 'https://www.dingtalk.com',
  type: 0,
  image:
    'https://img.alicdn.com/imgextra/i1/O1CN01SNHEw41ysQFPN5Ql6_!!6000000006634-55-tps-176-31.svg',
  title: '钉钉官网',
  content: '钉钉官网',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```