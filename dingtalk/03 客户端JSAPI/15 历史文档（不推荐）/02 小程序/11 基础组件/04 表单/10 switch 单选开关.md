---
title: "switch 单选开关"
source: "https://open.dingtalk.com/document/development/mini-app-switch-radio-switch-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-switch-radio-switch-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-switch-radio-switch-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍单选开关组件的使用。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| name | String | 组件名字，用于表单提交获取数据。 |
| checked | Boolean | 是否选中。 |
| disabled | Boolean | 是否禁用。 |
| color | String | 组件颜色。 |
| onChange | EventHandle | checked 改变时触发，event.detail={value:checked}。 |

## 示例代码

.axml示例代码：

```
  开关
```

.js示例代码：

```java
//  page/component/switch/switch.js
Page({
  data: {
    switch1: true,
  },
  switch1Change(e) {
    console.log('switch1 发生 change 事件，携带值为', e.detail.value);
    this.setData({
      switch1: e.detail.value,
    });
  },
  switch2Change(e){
    console.log('switch2 发生 change 事件，携带值为', e.detail.value);
  },
});
```

.acss示例代码：

```
/* page/component/switch/switch.acss */
.switch-item + .switch-item {
  margin-top: 20rpx;
}
```