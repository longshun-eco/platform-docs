---
title: "movable-area 可移动视图区域"
source: "https://open.dingtalk.com/document/development/mini-app-movable-area-movable-view-area"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 视图容器"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-movable-area-movable-view-area_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-movable-area-movable-view-area_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍可移动区域组件的使用。movable-area 必须设置 width 和 height 属性，不设置默认为 10px。

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| scale-area | Boolean | movable-view 设置为支持双指缩放时，设置此值可将缩放手势生效区域修改为整个 movable-area。  **默认值**：false。  **版本**：1.12.0及以上。 |

## 示例代码

.axml示例代码：

```
  可移动视图

    movable-view区域小于movable-area

        movable-view

    movable-view区域大于movable-area

        movable-view
```

.js示例代码：

```java
// page/component/movable-view.js
Page({
  data: {
    x: 0,
    y: 0,
  },
  onButtonTap() {
    const { x, y } = this.data;
    if (x === 30) {
      this.setData({
        x: x + 1,
        y: y + 1,
      });
    } else {
      this.setData({
        x: 30,
        y: 30
      });
    }
  },
});
```

.json示例代码：

```
// page/component/movable-view.json
{
  "allowsBounceVertical": "NO"
}
```

.acss 示例代码：

```
/* page/component/movable-view.acss */
movable-area {
  height: 400rpx;
  width: 400rpx;
  margin: 50rpx 0rpx 0 50rpx;
  background-color:  #ccc;
  overflow: hidden;
}

movable-view {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 200rpx;
  width: 200rpx;
  background:  #108ee9;
  color:  #fff;
}
.max {
  width: 600rpx;
  height: 600rpx;
```