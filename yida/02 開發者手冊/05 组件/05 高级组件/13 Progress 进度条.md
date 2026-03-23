---
title: "Progress 进度条"
source: "https://docs.aliwork.com/docs/developer/components/advanced/progress"
category: "開發者手冊 / 组件 / 高级组件"
updated: 
tags:
  - yida
  - 開發者手冊
---
## 何时使用

在操作需要较长时间才能完成时，为用户显示该操作的当前进度和状态。

-   操作在后台运行，需要耗费一定的客户端等待时间。
-   操作需要展示一个完成进度的百分比。

## 组件示例

## 组件属性

| 属性 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
|
hasBorder

 | 是否显示边框 | boolean | false |
|

percent

 | 设置百分比 | number | 0 |
|

progressive

 | 设置色彩阶段变化模式 | boolean | false |
|

shape

 | 进度条形态 | 'circle' | 'line' | 'line' |
|

size

 | 尺寸 | 'small' | 'medium' | 'large' | 'medium' |
|

state

 | 当前状态 | 'normal' | 'success' | 'error' | 'normal' |