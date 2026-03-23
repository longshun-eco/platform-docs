---
title: "radio 单选按钮"
source: "https://open.dingtalk.com/document/development/mini-app-radio-button-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-radio-button-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-radio-button-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍单选按钮组件的使用。

## 在线体验

## **属性**

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| value | String | 组件值，选中时 change 事件会携带的 value。 |
| checked | Boolean | 当前是否选中。  **默认值**：false。 |
| disabled | Boolean | 是否禁用。  **默认值**：false。 |

## **示例****代码**

.axml示例代码：

```
  单选框

              {{item.value}}
```

.js示例代码：

```
// page/component/radio/radio.js
Page({
  data: {
    items: [
      { name: 'angular', value: 'AngularJS' },
      { name: 'react', value: 'React', checked: true },
      { name: 'polymer', value: 'Polymer' },
      { name: 'vue', value: 'Vue.js' },
      { name: 'ember', value: 'Ember.js' },
      { name: 'backbone', value: 'Backbone.js', disabled: true },
    ],
  },
  onSubmit(e) {
    my.alert({
      content: e.detail.value.lib,
    });
    console.log('onSubmit', e.detail);
  },
  onReset(e) {
    console.log('onReset', e);
  },
```

.acss示例代码：

```
/*page/component/radio/radio.acss */
.radio {
  display: block;
  margin-bottom: 20rpx;
}
.radio-text {
  line-height: 1.8;
}
```