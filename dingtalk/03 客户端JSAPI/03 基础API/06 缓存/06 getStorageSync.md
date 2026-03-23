---
title: "getStorageSync"
source: "https://open.dingtalk.com/document/development/jsapi-get-storage-sync"
category: "客户端JSAPI / 基础API / 缓存"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-storage-sync_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-storage-sync_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用getStorageSync，同步获取缓存数据。

> 同步数据IO操作可能会影响小程序流畅度，建议使用异步接口，或谨慎处理调用异常。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10247) |

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
| key | String | 是 | city | 缓存数据的key。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| data | String | 杭州 | key对应的内容，不存在时返回 null。 |

## **示例****代码**

### 默认出入参

```javascript
const res = dd.getStorageSync({
  key: 'city',
});
const { data } = res;
```

返回对象示例：

```json
{ "data": "杭州" }
```