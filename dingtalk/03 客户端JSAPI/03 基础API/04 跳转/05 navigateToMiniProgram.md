---
title: "navigateToMiniProgram"
source: "https://open.dingtalk.com/document/development/jsapi-navigate-to-mini-program"
category: "客户端JSAPI / 基础API / 跳转"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-navigate-to-mini-program_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-navigate-to-mini-program_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用navigateToMiniProgram，跳转到其他钉钉小程序。

> 跳转到另一个钉钉小程序的最新线上版。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10192) |

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
| path | String | 否 | /pages/index/index | 打开目标小程序的页面路径。如果为空，则打开首页。 |
| appId | String | 是 | 54321 | 要跳转的目标小程要跳转的目标小程序miniAppId。  如果该参数值错误，会跳转到加载失败页面。 |
| extraData | Object | 否 | {"data1":"test"} | 需要传递给目标小程序的数据，为键值对的格式，数值的类型为字符串。  目标小程序可在 App.onLaunch()或 App.onShow()方法中获取到这份数据。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.navigateToMiniProgram({
  path: '/pages/index/index',
  appId: '54321',
  extraData: { data1: 'test' },
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```