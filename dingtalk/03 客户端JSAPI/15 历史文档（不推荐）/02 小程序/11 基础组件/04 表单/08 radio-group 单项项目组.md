---
title: "radio-group 单项项目组"
source: "https://open.dingtalk.com/document/development/mini-app-radio-group-individual-project-group-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-radio-group-individual-project-group-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-radio-group-individual-project-group-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍单项选择器组组件的使用。

单项选择器组内部由多个 radio 组成。

## 在线体验

## **属性**

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| onChange | EventHandle | 选中项发生变化时触发，`event.detail = {value: 选中项 radio 的 value}`。 |
| name | String | 组件名字，用于表单提交获取数据。 |

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