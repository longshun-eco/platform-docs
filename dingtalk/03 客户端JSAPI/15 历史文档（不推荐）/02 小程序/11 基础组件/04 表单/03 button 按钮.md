---
title: "button 按钮"
source: "https://open.dingtalk.com/document/development/mini-app-button-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 基础组件 / 表单"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-button-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-button-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍按钮组件的使用。

## 在线体验

## 属性

|  |  |  |
| --- | --- | --- |
| **属性** | **类型** | **描述** |
| size | String | 有效值 default、mini。  **默认值**：default。 |
| open-type | String | 开放能力。 |
| type | String | 按钮的样式类型，有效值 primary、default、warn。  **默认值**：default。 |
| plain | Boolean | 是否镂空。  **默认值**：false。 |
| disabled | Boolean | 是否禁用。  **默认值**：false。 |
| loading | Boolean | 按钮文字前是否带 loading 图标。  **默认值**：false。 |
| onTap | EventHandle | 点击。 |
| form-type | String | 有效值：submit、reset，用于表单组件，点击分别会触发 submit/reset 事件。 |
| hover-class | String | 按钮按下去的样式类。hover-class="none" 时表示没有点击态效果。  **默认值**：button-hover。 |
| hover-start-time | Number | 按住后多少时间后出现点击状态，单位毫秒。  **默认值**：20。 |
| hover-stay-time | Number | 手指松开后点击状态保留时间，单位毫秒。  **默认值**：70。 |

**重要**

`button-hover` 默认为 `{background-color: rgba(0, 0, 0, 0.1); opacity: 0.7;}`。

open-type 有效值:

|  |  |
| --- | --- |
| **值** | **说明** |
| share | 触发自定义分享，可使用[dd.canIUse](/document/orgapp/dd-caniuse)判断。 |

## 示例代码

.axml示例代码：

```
  按钮

    type-primary/ghost

    type-default
```

.js示例代码：

```
//pages/component/button.js
Page({
  data: {},
  onSubmit() {
    my.alert({ title: 'You click submit' });
  },
  onReset() {
    my.alert({ title: 'You click reset' });
  },
});
```

.acss示例代码：

```
/*pages/component/button .acss*/
.red {
  background-color:  red;
  border-color:  red;
  color:  #fff;
}

button + button {
  margin-top: 32rpx;
}
```