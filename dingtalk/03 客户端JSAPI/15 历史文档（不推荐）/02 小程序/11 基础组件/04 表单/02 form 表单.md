---
title: "form 表单"
source: "https://open.dingtalk.com/document/development/mini-app-form-form-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-form-form-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-form-form-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍表单组件的使用。

表单用于将组件内的用户输入的 `<textarea>`、 `<switch/>`、 `<input/>` 、`<checkbox-group/>`、`<slider/>`、`<radio-group/>`、`<picker/>` 等组件提交。

当点击 `form` 表单中 `formType` 为 `submit` 的 `button` 组件时，会将表单组件中的 `value` 值进行提交，需要在表单组件中加上 `name` 来作为 `key`。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| onSubmit | EventHandle | 携带 form 中的数据触发 submit 事件event.detail = {value : {'name': 'value'}}。 |
| onReset | EventHandle | 表单重置时会触发 reset 事件。 |
| class | String | 外部样式名。 |
| style | String | 内联样式。 |

## 示例代码

.axml示例代码：

```
  表单

      Slider

        Switch

        Input
```

.js示例代码：

```javascript
//page/component/form/form.js
Page({
  formSubmit: function(e) {
    console.log('form发生了submit事件，携带数据为：', e.detail.value)
  },
  formReset: function() {
    console.log('form发生了reset事件')
  }
})
```

.acss示例代码：

```
/*page/component/form/form.acss */
button + button {
  margin-top: 32rpx;
}
```