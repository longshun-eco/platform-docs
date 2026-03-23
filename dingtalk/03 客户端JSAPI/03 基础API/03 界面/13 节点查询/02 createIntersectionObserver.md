---
title: "createIntersectionObserver"
source: "https://open.dingtalk.com/document/development/jsapi-create-intersection-observer"
category: "客户端JSAPI / 基础API / 界面 / 节点查询"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-create-intersection-observer_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-create-intersection-observer_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用createIntersectionObserver，创建并返回一个IntersectionObserver对象实例。

> 需在page.onReady之后执行dd.createIntersectionObserver()。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10035) |

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
| selectAll | Boolean | 是 | false | 是否同时观测多个目标节点（而非一个），如果设为 true ，observe 的 targetSelector 将选中多个节点。  **默认值：** false。  同时选中过多节点将影响渲染性能。 |
| thresholds | Array<Number> | 是 | [0] | 一个数值数组，包含所有阈值。  默认值：[0]。 |
| initialRatio | Number | 是 | 0 | 初始的相交比例，如果调用时检测到的相交比例与这个值不相等且达到阈值，则会触发一次监听器的回调函数。  **默认值：** 0。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.createIntersectionObserver(true, [0], 0);
```