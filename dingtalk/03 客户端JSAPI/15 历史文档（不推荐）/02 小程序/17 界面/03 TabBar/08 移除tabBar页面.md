---
title: "移除tabBar页面"
source: "https://open.dingtalk.com/document/development/dd-removetabbaritem"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / TabBar"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-removetabbaritem_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-removetabbaritem_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.removeTabBarItem**移除tabBar页面。

**重要**

使用该接口请注意：

* removeTabBarItem 不可在非 tabBar 页面调用。
* removeTabBarItem 不可移除自身。
* removeTabBarItem 不可移除主 tab 页。

## **入参**

|  |  |  |  |
| --- | --- | --- | --- |
| **参数** | **类型** | **是否必填** | **说明** |
| index | number | 是 | 要删除的 item 对应的位置，从 0 开始。 |
| success | function | 否 | 接口调用成功的回调函数。 |
| fail | function | 否 | 接口调用失败的回调函数。 |
| complete | function | 否 | 接口调用结束的回调函数（调用成功、失败都会执行）。 |

## **什么是主 tabbar 页面**

当小程序被启动后，第一个被初始化的 tabBar 页面。

## **兼容性判断**

使用[dd.canIUse](/document/orgapp/dd-caniuse)('removeTabBarItem')进行兼容性判断。