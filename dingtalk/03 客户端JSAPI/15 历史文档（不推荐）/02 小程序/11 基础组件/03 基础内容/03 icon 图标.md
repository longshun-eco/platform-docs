---
title: "icon 图标"
source: "https://open.dingtalk.com/document/development/mini-app-icon-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 基础内容"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-icon-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-icon-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍图标组件的使用。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| type | String | icon 类型，有效值： info、warn、waiting、cancel、download、search、clear、success、success\_no\_circle。 |
| size | Number | icon 大小，单位px。  **默认值**：23。 |
| color | Color | icon 颜色，同 css 的 color。 |

## 示例代码

.axml示例代码：

```
  图标

    Type

          {{item}}

    Size
```

.js示例代码：

```
//page/component/icon.js
Page({
  data: {
    iconSize: [20, 30, 40, 50, 60],
    iconColor: [
      'red', 'yellow', 'blue', 'green',
    ],
    iconType: [
      'success',
      'info',
      'warn',
      'waiting',
      'clear',
      'success_no_circle',
      'download',
      'cancel',
      'search',
    ],
  },
});
```

.acss示例代码：

```
/*page/component/icon.acss*/
.icon-list {
  display: -webkit-flex;
  display: flex;
  -webkit-flex-wrap: wrap;
  flex-wrap: wrap;
}

.item {
  display: -webkit-flex;
  display: flex;
  flex-direction: column;
  -webkit-flex-direction: column;
  margin-bottom: 10px;
  margin-right: 10px;
  align-items: center;
  -webkit-align-items: center;
}
```