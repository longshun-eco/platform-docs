---
title: "text 文本"
source: "https://open.dingtalk.com/document/development/mini-app-text"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 基础内容"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-text_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-text_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍文本组件的使用。

组件内只支持 <text/> 嵌套。

## 在线体验

## 属性

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| selectable | Boolean | 是否可选。  **默认值**：false。 |
| class | String | 样式名。 |
| style | String | 内联样式。 |

## 示例代码

```json
    {{text}}
```

```
Page({
  data: {
    text: `钉钉是一种工作方式。
      酷公司，用钉钉。\n\n:)
    `,
  },
})
```