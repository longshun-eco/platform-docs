---
title: "异步获取指定key的缓存数据"
source: "https://open.dingtalk.com/document/development/dd-getstorage"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 缓存"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-getstorage_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-getstorage_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.getStorage**获取缓存数据，可以获取指定key的单条缓存数据。

## **示例代码**

```javascript
dd.getStorage({
  key: 'currentCity',
  success: function(res) {
    dd.alert({content: '获取成功：' + res.data.cityName});
  },
  fail: function(res){
    dd.alert({content: res.errorMessage});
  }
});
```

## **入参**

| **参数** | **类型** | **是否必填** | **说明** |
| --- | --- | --- | --- |
| key | String | 是 | 缓存数据的key。 |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Function | 否 | 调用结束的回调函数（调用成功、失败都会执行）。 |

**success返回值**

| **名称** | **类型** | **说明** |
| --- | --- | --- |
| data | Object/String | key对应的内容，不存在时返回 null。 |