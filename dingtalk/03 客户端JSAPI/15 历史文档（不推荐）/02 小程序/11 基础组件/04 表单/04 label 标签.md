---
title: "label 标签"
source: "https://open.dingtalk.com/document/development/mini-app-label-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-label-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-label-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍标签组件的使用。

`label`可以用来改进表单组件的可用性，使用 `for` 属性找到对应组件的 `id`，或者将组件放在该标签下，当点击时，就会聚焦对应的组件。

`for` 优先级高于内部组件，内部有多个组件的时候默认触发第一个组件。

目前可以绑定的控件有：`<checkbox/>`，`<radio/>`，`<input/>`，`<textarea/>`。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| for | String | 绑定组件的 id。 |
| class | String | 外部样式。 |
| style | String | 内联样式。 |

## 示例代码

.axml示例代码：

```
    Checkbox

             AngularJS

             React
```

.acss示例代码

```
/*page/component/label/label.acss */
checkbox-group > view,
radio-group > view {
  margin-bottom: 12rpx;
}
```