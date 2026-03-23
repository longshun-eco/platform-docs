---
title: "创建SelectorQuery节点查询对象"
source: "https://open.dingtalk.com/document/development/dd-createselectorquery"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 节点查询"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-createselectorquery_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-createselectorquery_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用dd.createSelectorQuery创建一个节点查询对象SelectorQuery。

## 扫码体验

![[development-dd-createselectorquery_p174248.png]]

## 使用限制

基础库 `1.4.0` 或更高版本。

## **示例代码**

.axml示例代码：

```
节点 all1

节点 all2

节点 one

  独立滚动区域
```

.js示例代码：

```sql
Page({
  onReady() {
    dd.createSelectorQuery()
      .select('#non-exists').boundingClientRect()
      .select('#one').boundingClientRect()
      .selectAll('.all').boundingClientRect()
      .select('#scroll').scrollOffset()
      .selectViewport().boundingClientRect()
      .selectViewport().scrollOffset().exec((ret) => {
      console.log(JSON.stringify(ret, null, 2));
    });
  },
});
```

**ret结构**

```
[
  null,
  {
    "x": 1,
    "y": 2,
    "width": 1367,
    "height": 18,
    "top": 2,
    "right": 1368,
    "bottom": 20,
    "left": 1
  },
  [
    {
      "x": 1,
      "y": -34,
      "width": 1367,
      "height": 18,
      "top": -34,
      "right": 1368,
      "bottom": -16,
```

## 入参

|  |  |  |
| --- | --- | --- |
| **参数** | **类型** | **说明** |
| params | object | 可以指定 page 属性，默认为当前页面。 |

## 返回值

[SelectorQuery](/document/orgapp/selectorquery)