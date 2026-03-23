---
title: "addTabBarItem"
source: "https://open.dingtalk.com/document/development/jsapi-add-tab-bar-item"
category: "客户端JSAPI / 基础API / 界面 / TabBar"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-add-tab-bar-item_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-add-tab-bar-item_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用addTabBarItem，添加tabBar页面。

使用该接口请注意：

* addTabBarItem最多调用90次。
* addTabBarItem 调用时，要保证当前小程序展示的是TabBar上的页面；否则调用会报错，错误码 11。
* addTabBarItem 不可对主 tabBar 页面进行替换。
* tabBar 最多为 5个。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10058) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| name | String | 是 | 日志 | tab标题。 |
| icon | String | 否 | /image/icon-hom.png | 图标。 |
| index | Number | 是 | 1 | tem插入位置，原位置的页面将后移一个位置，从 0 开始。 |
| activeIcon | String | 否 | /image/icon-home-selected.png | 选中时的图标。 |
| pagePath | String | 是 | pages/logs/logs | TabItem对应的页面路径，需要配置在小程序配置文件中。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.addTabBarItem({
  icon: '/image/icon-hom.png',
  name: '日志',
  index: 1,
  pagePath: 'pages/logs/logs',
  activeIcon: '/image/icon-home-selected.png',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```