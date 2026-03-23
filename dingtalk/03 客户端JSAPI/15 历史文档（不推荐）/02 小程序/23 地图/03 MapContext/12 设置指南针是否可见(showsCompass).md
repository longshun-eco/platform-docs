---
title: "设置指南针是否可见(showsCompass)"
source: "https://open.dingtalk.com/document/development/mapcontext-showscompass"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 地图 / MapContext"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mapcontext-showscompass_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mapcontext-showscompass_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17使用**MapContext.showsCompass**设置指南针是否可见。

## **示例代码**

```
this.mapCtx = dd.createMapContext('map');
this.mapCtx.showsCompass({isShowsCompass:1});
```

## **入参**

Object 类型，属性如下：

| **参数** | **类型** | **是否必填** | **说明** |
| --- | --- | --- | --- |
| isShowsCompass | Enum | 是 | 指南针是否可用。   * **1** ：表示可见 * **0**：表示不可见 |

## **兼容性**

使用 **dd.canIUse('createMapContext')**进行可用性判断。