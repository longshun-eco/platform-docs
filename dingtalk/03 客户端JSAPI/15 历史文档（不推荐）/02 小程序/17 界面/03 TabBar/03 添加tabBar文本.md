---
title: "添加tabBar文本"
source: "https://open.dingtalk.com/document/development/dd-settabbarbadge"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / TabBar"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-settabbarbadge_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-settabbarbadge_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.setTabBarBadge**为 tabBar 某一项的右上角添加文本。

## **示例代码**

```java
dd.setTabBarBadge({
  index: 0,
  text: '新'
})
```

## **入参**

| **参数** | **类型** | **是否必填** | **说明** |
| --- | --- | --- | --- |
| index | Number | 是 | tabBar 的哪一项，从左边算起。 |
| text | String | 是 | 显示的文本，超过 4 个字符则显示成 `...`。 |
| success | Function | 是 | 接口调用成功的回调函数。 |
| fail | Function | 否 | 接口调用失败的回调函数。 |
| complete | Function | 否 | 接口调用结束的回调函数（调用成功、失败都会执行）。 |