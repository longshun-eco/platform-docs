---
title: "显示tabBar红点"
source: "https://open.dingtalk.com/document/development/dd-showtabbarreddot"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / TabBar"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-showtabbarreddot_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-showtabbarreddot_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.showTabBarRedDot**显示tabBar某一项的右上角的红点。

## **示例代码**

```
dd.showTabBarRedDot({
  index: 0
})
```

## **入参**

| **参数** | **类型** | **是否必填** | **说明** |
| --- | --- | --- | --- |
| index | Number | 是 | tabBar 的哪一项，从左边算起。 |
| success | Function | 否 | 接口调用成功的回调函数。 |
| fail | Function | 否 | 接口调用失败的回调函数。 |
| complete | Function | 否 | 接口调用结束的回调函数（调用成功、失败都会执行）。 |