---
title: "removeCachedAPIResponse"
source: "https://open.dingtalk.com/document/development/jsapi-remove-cached-a-p-i-response"
category: "客户端JSAPI / 基础API / 设备 / 内存不足处理"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-remove-cached-a-p-i-response_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-remove-cached-a-p-i-response_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-16

删除已缓存的JSAPI返回值

清除当前页面上已缓存的 JSAPI 返回值，例如页面表单提交成功后，就可以清空之前的 JSAPI 缓存。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 8.0.15 | 不支持 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11930) |
| 小程序 | 不支持 | 8.0.15 | 不支持 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11930) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

在H5应用中，调用[dd.config](https://open.dingtalk.com/document/orgapp/jsapi-authentication)完成鉴权后使用

在小程序应用中，无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| jsapiName | String | 是 | biz.util.chooseImage | 需要清除的 JSAPI 名称 |
| removeAll | Boolean | 是 | true | 是否清除所有 JSAPI 的返回值缓存，默认 false |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认Demo标题

```
dd.removeCachedAPIResponse({
  jsapiName: 'biz.util.chooseImage',
  removeAll: false,
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```