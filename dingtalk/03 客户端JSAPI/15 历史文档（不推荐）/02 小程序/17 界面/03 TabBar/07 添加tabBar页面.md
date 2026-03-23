---
title: "添加tabBar页面"
source: "https://open.dingtalk.com/document/development/dd-addtabbaritem"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / TabBar"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-addtabbaritem_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-addtabbaritem_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.addTabBarItem**添加tabBar页面。

**重要**

使用该接口请注意：

* addTabBarItem最多调用90次。
* addTabBarItem 调用时，要保证当前小程序展示的是TabBar上的页面；否则调用会报错，错误码 11。
* addTabBarItem 不可对主 tabBar 页面进行替换。
* tabBar 最多为 5个。

## **入参说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **参数名** | **类型** | **是否必填** | **说明** |
| name | String | 是 | tab标题。 |
| icon | String | 否 | 图标。 |
| activeIcon | String | 否 | 选中时的图标。 |
| pagePath | String | 是 | TabItem对应的页面路径，需要配置在小程序配置文件中。 |
| index | Number | 是 | Item插入位置，原位置的页面将后移一个位置，从 0 开始。 |
| success | Function | 否 | 成功回调。 |
| fail | Function | 否 | 失败回调。 |
| complete | Function | 否 | 成功或失败回调。 |

## **什么是主 tabbar 页面**

当小程序被启动后，第一个被初始化的 tabBar 页面。

## **兼容性判断**

使用[dd.canIUse](/document/orgapp/dd-caniuse)('addTabBarItem')进行兼容性判断 。