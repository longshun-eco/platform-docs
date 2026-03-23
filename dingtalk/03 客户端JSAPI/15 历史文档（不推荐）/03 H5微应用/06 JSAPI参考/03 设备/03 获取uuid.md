---
title: "获取uuid"
source: "https://open.dingtalk.com/document/development/get-uuid"
category: "客户端JSAPI / 历史文档（不推荐） / H5微应用 / JSAPI参考 / 设备"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-get-uuid_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-get-uuid_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**device.base.getUUID**获取uuid。

## 调试

访问[JSAPI Explorer](https://open-dev.dingtalk.com/apiExplorer#/jsapi?api=device.base.getUUID)在线调试该接口。

## 使用说明

调用本接口前，请先引入钉钉js，参考[准备工作](/document/orgapp/read-before-development)。

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **客户端** | **是否需要鉴权** | **Android** | **iOS** | **PC** |
| 支持说明 | 需要 | 支持 | 支持 | 不支持 |

```javascript
dd.device.base.getUUID({
    onSuccess : function(data) {
        /*
        {
            uuid: '3udbhg98ddlljokkkl' //
        }
        */
    },
    onFail : function(err) {}
});
```

## 返回结果

|  |  |
| --- | --- |
| 参数 | 说明 |
| uuid | 通用唯一识别码。 |