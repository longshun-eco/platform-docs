---
title: "openPageInSlidePanelForPC"
source: "https://open.dingtalk.com/document/development/jsapi-open-page-in-slide-panel-for-pc"
category: "客户端JSAPI / 基础API / 跳转"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-open-page-in-slide-panel-for-pc_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-open-page-in-slide-panel-for-pc_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用openPageInSlidePanelForPC打开侧边面板。

![[development-jsapi-open-page-in-slide-panel-for-pc_O1CN01QUbymJ1ytnUNlmG8H_!!6000000006637-2-tps-1622-1712.png]]

> * 面板内页面调用quitPage时，接口会进入success回调, result为调用quitPage传入的数值。
> * 点击右上角上角关闭按钮会进入fail 回调。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11695) |
| 小程序 | 不支持 | 不支持 | 不支持 | 不支持 | - |

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
| url | String | 是 | https://www.dingtalk.com | 打开侧边栏的url。 |
| title | String | 是 | title | 侧边栏顶部标题。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.openPageInSlidePanelForPC({
  url: 'https://www.dingtalk.com',
  title: '钉钉',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```