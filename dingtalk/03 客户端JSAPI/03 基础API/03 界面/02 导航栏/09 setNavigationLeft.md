---
title: "setNavigationLeft"
source: "https://open.dingtalk.com/document/development/jsapi-set-navigation-left"
category: "客户端JSAPI / 基础API / 界面 / 导航栏"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-set-navigation-left_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-set-navigation-left_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用setNavigationLeft设置左侧导航按钮文本。

![[development-jsapi-set-navigation-left_p177959.png]]

如图设置左侧操作区的文案和行为

PC端：只在SlidePanel里起作用

PC端左侧按钮点击事件，添加监听回调函数

```
//添加监听回调函数
dd.on('leftBtnClick', handleFn);
```

左侧按钮点击事件，移除相应handleFn的监听回调函数

```
//移除相应handleFn的监听回调函数
dd.off('leftBtnClick', handleFn);
```

该API在Android、iOS端半屏容器中不予支持。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11610) |
| 小程序 | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |

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
| text | String | 是 | 返回 | 控制显示文本，空字符串表示显示默认文本。 |
| control | Boolean | 否 | true | 是否控制点击事件(PC端不可用)：   * true：控制 * false（默认）：不控制 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```java
dd.setNavigationLeft({
  text: '返回',
  control: true,
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```