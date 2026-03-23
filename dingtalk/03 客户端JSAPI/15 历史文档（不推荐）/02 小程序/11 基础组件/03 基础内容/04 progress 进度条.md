---
title: "progress 进度条"
source: "https://open.dingtalk.com/document/development/mini-app-progress-progress-bar-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 基础内容"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-progress-progress-bar-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-progress-progress-bar-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍进度条组件的使用。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| percent | Float | 百分比(0~100)。 |
| show-info | Boolean | 在右侧显示百分比值。  **默认值**：false。 |
| stroke-width | Number | 线的粗细，单位 px。  **默认值**：6px。 |
| activeColor | Color | 已选择的进度条颜色。  **默认****值**：#09BB07。 |
| backgroundColor | Color | 未选择的进度条颜色。 |
| active | Boolean | 从左往右是否进行加载动画。  **默认值**：false。 |

## 示例代码

.axml示例代码：

```
  进度条
```

.acss示例代码：

```
/*page/component/progress.acss*/
progress{
  margin-bottom: 60rpx;
}
```