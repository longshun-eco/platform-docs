---
title: "swiper 滑块视图容器"
source: "https://open.dingtalk.com/document/development/mini-app-swiper-slider-view-container"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 视图容器"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-swiper-slider-view-container_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-swiper-slider-view-container_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍滑块视图容器组件的使用。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| indicator-dots | Boolean | 是否显示指示点。  **默认值**：false。 |
| indicator-color | Color | 指示点颜色。  **默认值**：rgba(0, 0, 0, .3)。 |
| indicator-active-color | Color | 当前选中的指示点颜色。  **默认值**：#000。 |
| autoplay | Boolean | 是否自动切换。  **默认值**：false。 |
| current | Number | 当前页面的 index。  **默认值**：0。 |
| duration | Number | 滑动动画时长。  **默认值**：500(ms)。 |
| interval | Number | 自动切换时间间隔。  **默认值**：5000(ms)。 |
| circular | Boolean | 是否启用无限滑动。  **默认值**：false。 |
| vertical | Boolean | 滑动方向是否为纵向。  **默认值**：false。 |
| onChange | Function | current 改变时会触发，event.detail = {current: current}。  **默认值**：否。 |

## 示例代码

**swiper-item**

仅可放置在组件中，宽高自动设置为100%。

.axml示例代码：

```
  滑块视图容器
```

.js示例代码：

```java
//page/component/swiper.js
Page({
  data: {
    background: ['blue', 'red', 'yellow'],
    indicatorDots: true,
    autoplay: false,
    vertical: false,
    interval: 1000,
    circular: false,
  },
  onLoad() {
  },
  changeIndicatorDots(e) {
    this.setData({
      indicatorDots: !this.data.indicatorDots,
    });
  },
  changeVertical() {
    this.setData({
      vertical: !this.data.vertical,
    });
```

.json示例代码：

```
//page/component/swiper.json
{
  "defaultTitle": "Swiper",
  "pullRefresh": false,
  "allowsBounceVertical": false
}
```

.acss示例代码：

```
/* page/component/swiper.acss */
.swiper-item{
  display: block;
  height: 150px;
  margin:10px;
}
.margin-t {
  margin-top: 24px;
}
```