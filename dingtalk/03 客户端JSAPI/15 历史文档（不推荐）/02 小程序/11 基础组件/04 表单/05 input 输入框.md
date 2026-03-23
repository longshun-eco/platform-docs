---
title: "input 输入框"
source: "https://open.dingtalk.com/document/development/mini-app-basic-components-input-box-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-basic-components-input-box-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-basic-components-input-box-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍输入框组件的使用。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| value | String | 初始内容。 |
| name | String | 组件名字，用于表单提交获取数据。 |
| class | String | 外部样式名。 |
| style | String | 内联样式。 |
| type | String | input 的类型，有效值：text、search。  **默认值**：text。 |
| password | Boolean | 是否是密码类型。  **默认值**：false。 |
| placeholder | String | 占位符。 |
| disabled | Boolean | 是否禁用。  **默认值**：false。 |
| maxlength | Number | 最大长度。  **默认值**：140。 |
| onInput | EventHandle | 键盘输入时触发input事件，event.detail = {value: value}。 |
| onConfirm | EventHandle | 点击键盘完成（Enter）时触发，event.detail = {value: value}。 |
| onFocus | EventHandle | 聚焦时触发，event.detail = {value: value}。 |
| onBlur | EventHandle | 失去焦点时触发，event.detail = {value: value}。 |

## 示例代码

.axml示例代码：

```
  输入框

      受控聚焦

      显示输入
```

.js示例代码：

```java
//page/component/input/input.js
Page({
  data: {
    focus: false,
    inputValue: '',
  },
  bindButtonTap() {
    // blur 事件和这个冲突
    setTimeout(() => {
      this.onFocus();
    }, 100);
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
```

.acss示例代码：

```
/*page/component/input/input.acss */
.extra-info {
  border-top: 1px solid  #ddd;
  margin-left: 30rpx;
  padding: 20rpx 0;
  overflow: auto;
}
.search-outer {
  box-sizing: border-box;
  display:flex;
  height:40px;
  overflow:hidden;
  padding: 8px;
  border-bottom: 1px solid  #ddd;
  background-color:  #efeff4;
}
.search-outer * {
  box-sizing: border-box;
}
.search-input {
  flex:1;
```