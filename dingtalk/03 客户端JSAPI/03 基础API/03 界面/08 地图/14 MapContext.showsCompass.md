---
title: "MapContext.showsCompass"
source: "https://open.dingtalk.com/document/development/jsapi-map-context-shows-compass"
category: "客户端JSAPI / 基础API / 界面 / 地图"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-map-context-shows-compass_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-map-context-shows-compass_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

使用MapContext.showsCompass设置指南针是否可见。

### 兼容性

使用 dd.canIUse('createMapContext')进行可用性判断。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10131) |

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
| isShowsCompass | Number | 是 | 0 | 指南针是否可用。   * 1 ：表示可见 * 0：表示不可见 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```javascript
const mapContext = dd.createMapContext();

mapContext.showsCompass({
  isShowsCompass: 0,
});
```