---
title: "scroll-view 可滚动视图区域"
source: "https://open.dingtalk.com/document/development/mini-app-scroll-view-the-scrollable-area"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 视图容器"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-scroll-view-the-scrollable-area_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-scroll-view-the-scrollable-area_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍可滚动视图区域组件的使用。

**重要**

* scroll-into-view 的优先级高于 scroll-top。
* 在滚动 scroll-view 时会阻止页面回弹，所以在 scroll-view 中滚动，是无法触发 onPullDownRefresh。

**扫码体验**

![[development-mini-app-scroll-view-the-scrollable-area_p169755.png]]

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| class | String | 外部样式名。 |
| style | String | 内联样式名。 |
| scroll-x | Boolean | 是否允许横向滚动。  **默认值**：false。 |
| scroll-y | Boolean | 是否允许纵向滚动。  **默认值**：false。 |
| upper-threshold | Number | 距顶部/左边多少距离时（px）触发。  **默认值**：50px。 |
| lower-threshold | Number | 距底部/右边多少距离时（px）触发。  **默认值**：50px。 |
| scroll-top | Number | 竖向滚动条位置。 |
| scroll-left | Number | 横向滚动条位置。 |
| scroll-into-view | String | 值为某个子元素的 id，滚动到该元素，元素顶部对齐滚动区域顶部。 |
| scroll-with-animation | Boolean | 是否在设置滚动条位置时使用动画过渡。  **默认值**：false。 |
| onScrollToUpper | EventHandle | 滚动到顶部/左边时触发。 |
| onScrollToLower | EventHandle | 滚动到底部/右边时触发。 |
| onScroll | EventHandle | 滚动时触发event.detail = {scrollLeft, scrollTop, scrollHeight, scrollWidth, deltaX, deltaY}。 |

**重要**

使用竖向滚动时，需要给一个固定高度，通过 acss 设置 height。

## 示例代码

.axml示例代码：

```
  可滚动视图区域

    vertical scroll

      next
      move
      scrollToTop
```

.js示例代码：

```java
//page/component/scroll-view.js
const order = ['blue', 'red', 'green', 'yellow'];

Page({
  data: {
    toView: 'red',
    scrollTop: 100,
  },
  upper(e) {
    console.log(e);
  },
  lower(e) {
    console.log(e);
  },
  scroll(e) {
    this.setData({
      scrollTop: e.detail.scrollTop,
    });
  },
  scrollEnd() {
```

.json示例代码：

```
// page/component/scroll-view.json
{
  "defaultTitle": "Scroll View"
}
```

.acss示例代码：

```
/* page/component/swiper-view.acss */
.scroll-view_H {
  white-space: nowrap;
  display:flex;
}
.scroll-view-item {
  height: 200px;
}
.scroll-view-item_H {
  flex-shrink:0;
  flex-grow:0;
  width: 300px;
  height: 200px;
}
```