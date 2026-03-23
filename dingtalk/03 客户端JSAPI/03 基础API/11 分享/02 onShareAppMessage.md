---
title: "onShareAppMessage"
source: "https://open.dingtalk.com/document/development/jsapi-on-share-app-message"
category: "客户端JSAPI / 基础API / 分享"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-on-share-app-message_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-on-share-app-message_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

在Page中定义onShareAppMessage函数，用来自定义该页面的分享内容。此时该页面右上角菜单中会显示分享按钮，反之不显示。

用户点击分享按钮时才会调用此事件。
此事件需要return一个Object，用于自定义分享内容。

扫码体验

![[development-jsapi-on-share-app-message_p163583.png]]

分享卡片规范

![[development-jsapi-on-share-app-message_p338530.png]]

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| H5 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10021) |

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
| desc | String | 否 | 小程序官方示例Demo，展示已支持的接口能力及组件。 | 自定义分享描述。 |
| path | String | 是 | page/component/component-pages/view/view?param=123 | 自定义分享页面的路径，path中的自定义参数可在小程序生命周期的onLoad方法中获取（参数传递遵循http get的传参规则）。 |
| imageUrl | String | 否 | https://gw.alicdn.com/imgextra/i3/O1CN01Eg6xCm1nnsXZCnkP4\_!!6000000005135-2-tps-200-200.png | 自定义分享图片(只支持网络图片路径)。 |
| fallbackUrl | String | 否 | https://dingtalk.com | 可降级 H5 URL，仅适用于企业应用。当前钉钉桌面客户端不支持打开企业类小程序，配置此设置后，在桌面端访问此企业应用时，会打开fallbackUrl配置的H5 URL。 |
| desktopContainerType | String | 否 | side\_panel | 当前只支持 "side\_panel" ，表示在 桌面端使用 side\_panel 钉钉容器打开 fallbackUrl 。需要和 fallbackUrl 配合使用。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
Page({
  onShareAppMessage() {
    return {
      title: '小程序示例',
      desc: '小程序官方示例Demo，展示已支持的接口能力及组件。',
      path: 'page/component/component-pages/view/view?param=123',
    };
  },
});
```