---
title: "CanvasContext.toTempFilePath"
source: "https://open.dingtalk.com/document/development/jsapi-canvas-context-to-temp-file-path"
category: "客户端JSAPI / 基础API / 界面 / 画布"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-canvas-context-to-temp-file-path_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-canvas-context-to-temp-file-path_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用CanvasContext.toTempFilePath，把画布内容导出成图片。

> 使用CanvasContext.toTempFilePath把当前画布的内容导出生成图片，并返回文件路径。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10118) |

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
| x | Number | 否 | 0 | 画布 x 轴起点。 默认值： 0。 |
| y | Number | 否 | 0 | 画布 y 轴起点。 默认值： 0。 |
| width | Number | 否 | 0 | 画布宽度。 默认值：canvas 宽度 - x。 |
| height | Number | 否 | 100 | 画布高度。 默认值：canvas 高度 - y。 |
| destWidth | Number | 否 | 100 | 输出的图片宽度。 默认值：width。 |
| destHeight | Number | 否 | 100 | 输出的图片高度。 默认值：height。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| url | String | https://example.com | 返回文件路径。 |

## **示例****代码**

### 默认出入参

```javascript
const res = dd.CanvasContext.toTempFilePath({
  x: 0,
  y: 0,
  width: 0,
  height: 100,
  destWidth: 100,
  destHeight: 100,
});
const { url } = res;
```

返回对象示例：

```json
{ "url": "https://example.com" }
```