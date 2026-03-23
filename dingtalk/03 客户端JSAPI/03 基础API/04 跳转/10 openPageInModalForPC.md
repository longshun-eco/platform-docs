---
title: "openPageInModalForPC"
source: "https://open.dingtalk.com/document/development/jsapi-open-page-in-modal-for-pc"
category: "客户端JSAPI / 基础API / 跳转"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-open-page-in-modal-for-pc_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-open-page-in-modal-for-pc_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用openPageInModalForPC打开模态框。

支持大、中、小三种尺寸的模态框，来打开目标页面。

| 模态框尺寸 | size输入 | 长宽 |
| --- | --- | --- |
| 大模态框 （默认） |  | 包括标题 676px \* 545px |
| 中模态框 | middle | 包括标题 440px \* 300px |
| 小模态框 | mini | 包括标题 366px \* 120px |

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11696) |
| 小程序 | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |

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
| url | String | 是 | https://test.dingtalk.com/modal.html | 模态框内部显示内容的url。 |
| size | String | 否 | middle | 模态框的尺寸大小：   * 不填：使用默认值，676px \* 545px。 * middle：440px \* 300px。 * mini：366px \* 120px。 |
| title | String | 是 | modal title | 模态框标题。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.openPageInModalForPC({
  url: 'https://test.dingtalk.com/modal.html',
  size: 'middle',
  title: 'modal title',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```