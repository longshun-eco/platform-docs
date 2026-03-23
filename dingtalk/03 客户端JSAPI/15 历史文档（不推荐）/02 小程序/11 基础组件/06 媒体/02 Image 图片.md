---
title: "Image 图片"
source: "https://open.dingtalk.com/document/development/mini-app-image-media-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 媒体"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-image-media-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-image-media-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍图片组件的介绍。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| src | String | 图片地址。 |
| mode | String | 图片模式。mode 有 13 种模式，其中 4 种是缩放模式，9 种是裁剪模式。  **默认值**：scaleToFill。 |
| class | String | **默认值**：外部样式。 |
| style | String | **默认值**：内联样式。 |
| onError | HandleEvent | 当图片加载错误时触发，事件对象event.detail = {errMsg: 'something wrong'}。 |
| onLoad | HandleEvent | 图片载入完毕时触发，事件对象event.detail = {height:'图片高度px', width:'图片宽度px'}。 |

**重要**

`image` 组件默认宽度 300px、高度 225px。

## 缩放模式

| **属性** | **描述** |
| --- | --- |
| scaleToFill | 不保持纵横比缩放，使图片的宽高完全拉伸至填满 image 元素。 |
| aspectFit | 保持纵横比缩放，使图片的长边能完全显示出来。也就是说，可以完整地将图片显示出来。 |
| aspectFill | 保持纵横比缩放，只保证图片的短边能完全显示出来。也就是说，图片通常只在水平或垂直方向是完整的，另一个方向将会发生截取。 |
| widthFix | 宽度不变，高度自动变化，保持原图宽高比不变。 |

## 裁剪模式

| **属性** | **描述** |
| --- | --- |
| top | 不缩放图片，只显示顶部区域。 |
| bottom | 不缩放图片，只显示底部区域。 |
| center | 不缩放图片，只显示中间区域。 |
| left | 不缩放图片，只显示左边区域。 |
| right | 不缩放图片，只显示右边区域。 |
| top left | 不缩放图片，只显示左上边区域。 |
| top right | 不缩放图片，只显示右上边区域。 |
| bottom left | 不缩放图片，只显示左下边区域。 |
| bottom right | 不缩放图片，只显示右下边区域。 |

**重要**

图片高度不能设置为 auto，如果需要图片高度为 auto，直接设置 mode 为 widthFix。

## 示例代码

.axml示例代码：

```
  图片

    {{item.text}}
```

.js示例代码：

```
Page({
  data: {
    array: [{
      mode: 'scaleToFill',
      text: 'scaleToFill：不保持纵横比缩放图片，使图片完全适应',
    }, {
      mode: 'aspectFit',
      text: 'aspectFit：保持纵横比缩放图片，使图片的长边能完全显示出来',
    }, {
      mode: 'aspectFill',
      text: 'aspectFill：保持纵横比缩放图片，只保证图片的短边能完全显示出来',
    }, {
      mode: 'widthFix',
      text: 'widthFix：宽度不变，高度自动变化，保持原图宽高比不变',
    }, {
      mode: 'top',
      text: 'top：不缩放图片，只显示图片的顶部区域',
    }, {
      mode: 'bottom',
      text: 'bottom：不缩放图片，只显示图片的底部区域',
    }, {
```

.acss示例代码：

```
.page-section-demo {
  display: flex;
  justify-content: space-around;
}
.image {
  background-color:  red;
  width: 100px;
  height: 100px;
}
```