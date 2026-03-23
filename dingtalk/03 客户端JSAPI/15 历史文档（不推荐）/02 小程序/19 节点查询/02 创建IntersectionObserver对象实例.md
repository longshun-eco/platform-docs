---
title: "创建IntersectionObserver对象实例"
source: "https://open.dingtalk.com/document/development/dd-createintersectionobserver"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 节点查询"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-createintersectionobserver_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-createintersectionobserver_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.createIntersectionObserver**创建并返回一个IntersectionObserver对象实例。需在page.onReady之后执行dd.createIntersectionObserver()。

## 使用限制

基础库 1.24.0 及以上版本，低版本需做兼容处理。

## 入参

入参为 Object 类型，属性如下：

|  |  |  |
| --- | --- | --- |
| **参数** | **类型** | **说明** |
| thresholds | Number[] | 一个数值数组，包含所有阈值。  **默认值**：[0]。 |
| initialRatio | Number | 初始的相交比例，如果调用时检测到的相交比例与这个值不相等且达到阈值，则会触发一次监听器的回调函数。  **默认值**：0。 |
| selectAll | Boolean | 是否同时观测多个目标节点（而非一个），如果设为 true ，observe 的 targetSelector 将选中多个节点。  **默认值**：false。  **重要**  同时选中过多节点将影响渲染性能。 |

## **返回值**

[IntersectionObserver](/document/orgapp/overview-of-intersectionobserver)