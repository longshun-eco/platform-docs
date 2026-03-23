---
title: "同步获取指定key的缓存数据"
source: "https://open.dingtalk.com/document/development/dd-getstoragesync"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 缓存"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-getstoragesync_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-getstoragesync_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.getStorageSync**同步获取缓存数据。

**重要**

同步数据IO操作可能会影响小程序流畅度，建议使用异步接口，或谨慎处理调用异常。

## **示例****代码**

```javascript
 let res = dd.getStorageSync({ key: 'currentCity' });
 dd.alert({
    content: JSON.stringify(res.data),
 });
```

## **入参**

| **参数** | **类型** | **是否必填** | **说明** |
| --- | --- | --- | --- |
| key | String | 是 | 缓存数据的key。 |

## **返回值**

| **名称** | **类型** | **说明** |
| --- | --- | --- |
| data | Object/String | key对应的内容，不存在时返回 null。 |