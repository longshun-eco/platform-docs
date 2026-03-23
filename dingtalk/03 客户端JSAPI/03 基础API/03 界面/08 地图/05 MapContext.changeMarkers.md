---
title: "MapContext.changeMarkers"
source: "https://open.dingtalk.com/document/development/jsapi-map-context-change-markers"
category: "客户端JSAPI / 基础API / 界面 / 地图"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-map-context-change-markers_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-map-context-change-markers_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

使用MapContext.changeMarkers用于添加、删除、更新指定的标记（marker）。

## 兼容性

使用 dd.canIUse('createMapContext.return.changeMarkers')进行可用性判断。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10123) |

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
| add | Array<Object> | 否 | [{ iconPath: "/image/green\_tri.png", id: 10, latitude: 30.279383, longitude: 120.131441, width: 50, height: 50 },{ iconPath: "/image/green\_tri.png", id: 10, latitude: 30.279383, longitude: 120.131441, width: 50, height: 50, customCallout: { type: 1, time: '1', }, fixedPoint:{ originX: 400, originY: 400, }, iconAppendStr: '黄龙时代广场黄龙时代广场黄龙时代广场黄龙时代广场test' }] | 需要添加的 marker 数组。 |
| remove | Array<Object> | 否 | [{ iconPath: "/image/green\_tri.png", id: 10, latitude: 30.279383, longitude: 120.131441, width: 50, height: 50 },{ iconPath: "/image/green\_tri.png", id: 10, latitude: 30.279383, longitude: 120.131441, width: 50, height: 50, customCallout: { type: 1, time: '1', }, fixedPoint:{ originX: 400, originY: 400, }, iconAppendStr: '黄龙时代广场黄龙时代广场黄龙时代广场黄龙时代广场test' }] | 需要删除的 marker 数组。 |
| update | Array<Object> | 否 | [{ iconPath: "/image/green\_tri.png", id: 10, latitude: 30.279383, longitude: 120.131441, width: 50, height: 50 },{ iconPath: "/image/green\_tri.png", id: 10, latitude: 30.279383, longitude: 120.131441, width: 50, height: 50, customCallout: { type: 1, time: '1', }, fixedPoint:{ originX: 400, originY: 400, }, iconAppendStr: '黄龙时代广场黄龙时代广场黄龙时代广场黄龙时代广场test' }] | 需要更新的 marker 数组。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 新增标记

```javascript
const mapContext = dd.createMapContext();

mapContext.changeMarkers({
  add: [
    {
      iconPath: '/image/green_tri.png',
      id: 10,
      latitude: 30.279383,
      longitude: 120.131441,
      width: 50,
      height: 50,
    },
    {
      iconPath: '/image/green_tri.png',
      id: 10,
      latitude: 30.279383,
      longitude: 120.131441,
      width: 50,
      height: 50,
      customCallout: {
        type: 1,
```

### 修改标记

```javascript
const mapContext = dd.createMapContext();

mapContext.changeMarkers({
  update: [
    {
      iconPath: '/image/green_tri.png',
      id: 10,
      latitude: 30.279383,
      longitude: 120.131441,
      width: 50,
      height: 50,
    },
    {
      iconPath: '/image/green_tri.png',
      id: 10,
      latitude: 30.279383,
      longitude: 120.131441,
      width: 50,
      height: 50,
      customCallout: { type: 1, time: '1' },
      fixedPoint: { originX: 400, originY: 400 },
```

### 删除标记

```javascript
const mapContext = dd.createMapContext();

mapContext.changeMarkers({
  remove: [
    {
      iconPath: '/image/green_tri.png',
      id: 10,
      latitude: 30.279383,
      longitude: 120.131441,
      width: 50,
      height: 50,
    },
    {
      iconPath: '/image/green_tri.png',
      id: 10,
      latitude: 30.279383,
      longitude: 120.131441,
      width: 50,
      height: 50,
      customCallout: { type: 1, time: '1' },
      fixedPoint: { originX: 400, originY: 400 },
```