---
title: "picker view 滚动选择器"
source: "https://open.dingtalk.com/document/development/mini-app-picker-view-scroll-selector-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-picker-view-scroll-selector-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-picker-view-scroll-selector-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍滚动选择器（嵌入页面内）的使用。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| value | Number Array | 数字表示 picker-view-column 中对应的 index （从 0 开始）。 |
| indicatorStyle | String | 选中框样式。 |
| onChange | EventHandle | 滚动选择 value 改变时触发，event.detail = {value: value}；value为数组，表示 picker-view 内的 picker-view-column index 索引，从 0 开始。 |

**重要**

其中只可放置组件，其他节点不会显示。该组件请勿放入 hidden 或 display none 的节点内部，需要隐藏请用 a:if 切换。

不推荐：

推荐：

## 示例代码

.axml示例代码：

```
        2013
        2014

        春
        夏

    {{value}}
```

.js示例代码：

```java
Page({
  data: {},
  onChange(e) {
    console.log(e.detail.value);
    this.setData({
      value: e.detail.value,
    });
  },
});
```