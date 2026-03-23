---
title: "picker底部弹起的滚动选择器"
source: "https://open.dingtalk.com/document/development/mini-app-scroll-picker-that-pops-up-on-the-bottom-of-the-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-scroll-picker-that-pops-up-on-the-bottom-of-the-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-scroll-picker-that-pops-up-on-the-bottom-of-the-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-13本文介绍滚动选择器（从底部弹起）组件的使用。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| range | String[] / Object[] | String[] 时表示可选择的字符串列表 Object[] 时需指定 range-key 表示可选择的字段。  **默认值**：[]。 |
| range-key | String | 当 range 是一个 Object[] 时，通过 range-key 来指定 Object 中 key 的值作为选择器显示内容。 |
| value | Number | 表示选择了 range 中的第几个（下标从 0 开始）。 |
| onChange | EventHandle | value 改变时触发，event.detail = {value: value}。 |
| disabled | Boolean | 是否禁用。  **默认值**：false。 |

## 示例代码

.axml示例代码：

```
  选择器

        地区选择器
        当前选择：{{array[index]}}

        ObjectArray
        当前选择：{{objectArray[arrIndex].name}}
```

.js示例代码：

```
//page/component/picker/picker.js
Page({
  data: {
    array: ['中国', '美国', '巴西', '日本'],
    objectArray: [
      {
        id: 0,
        name: '美国',
      },
      {
        id: 1,
        name: '中国',
      },
      {
        id: 2,
        name: '巴西',
      },
      {
        id: 3,
        name: '日本',
      },
```

.acss示例代码：

```
/* page/component/picker/picker.acss */
.date-radio {
  padding: 26rpx;
}

.date-radio label + label {
  margin-left: 20rpx;
}

.row {
  display: flex;
  align-items: center;
  padding: 0 30rpx;
}

.row-title {
  flex: 1;
  padding-top: 28rpx;
  padding-bottom: 28rpx;
  font-size: 34rpx;
```