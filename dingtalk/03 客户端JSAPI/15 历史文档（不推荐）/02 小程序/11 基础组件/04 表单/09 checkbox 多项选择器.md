---
title: "checkbox 多项选择器"
source: "https://open.dingtalk.com/document/development/mini-app-checkbox-multiple-selectors-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-checkbox-multiple-selectors-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-checkbox-multiple-selectors-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍多项选择器组件的使用。

## 在线体验

## 属性

多选项目。

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| value | String | 组件值，选中时 change 事件会携带的 value。 |
| checked | Boolean | 当前是否选中，可用来设置默认选中。  **默认****值**：false。 |
| disabled | Boolean | 是否禁用。  **默认值**：false。 |
| onChange | EventHandle | 组件发生改变时触发，detail = {value: 该 checkbox 是否 checked}。 |

## **示例****代码**

.axml示例代码：

```
  多项选择器

      选择你用过的框架：

            {{item.value}}
```

.js示例代码：

```
//  page/component/checkbox/checkbox.js
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
    console.log('onSubmit', e);
    my.alert({
      content: `你选择的框架是 ${e.detail.value.libs.join(', ')}`,
    });
  },
  onReset(e) {
    console.log('onReset', e);
  },
```

.acss示例代码：

```
/*page/component/checkbox/checkbox.acss */
.checkbox {
  display: block;
  margin-bottom: 20rpx;
}

button + button {
  margin-top: 32rpx;
}

.checkbox-text {
  font-size:34rpx;
  line-height: 1.2;
}
```