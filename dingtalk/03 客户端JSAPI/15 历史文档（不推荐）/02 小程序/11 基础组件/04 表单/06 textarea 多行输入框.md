---
title: "textarea 多行输入框"
source: "https://open.dingtalk.com/document/development/mini-app-textarea-multi-line-input-box-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-textarea-multi-line-input-box-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-textarea-multi-line-input-box-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍多行输入框组件的使用。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| name | String | 组件名字，用于表单提交获取数据。 |
| value | String | 初始内容。 |
| placeholder | String | 占位符。 |
| class | String | 样式名。 |
| style | String | 内联样式。 |
| disabled | Boolean | 是否禁用。  **默认值**：false。 |
| maxlength | Number | 最大长度，当设置为-1时不限制最大长度。  **默认值**：140。 |
| focus | Boolean | 获取焦点。  **默认值**：false。 |
| auto-height | Boolean | 是否自动增高。  **默认值**：false。 |
| onInput | EventHandle | 键盘输入时触发，event.detail = {value: value}。 |
| onFocus | EventHandle | 输入框聚焦时触发 event.detail = {value: value}。 |
| onBlur | EventHandle | 输入框失去焦点时触发，event.detail = {value: value}。 |
| onConfirm | EventHandle | 点击完成时触发，event.detail = {value: value}。 |

## 示例代码

.axml示例代码：

```
  文本框

    受控聚焦

    自适应高度

    结合表单
```

.js示例代码：

```java
//page/component/textarea/textarea.js
Page({
  data: {
    height: 20,
    focus: false,
  },
  bindButtonTap() {
    this.onFocus();
  },
  onFocus() {
    this.setData({
      focus: true,
    });
  },
  onBlur() {
    this.setData({
      focus: false,
    });
  },

  bindTextAreaBlur(e) {
```