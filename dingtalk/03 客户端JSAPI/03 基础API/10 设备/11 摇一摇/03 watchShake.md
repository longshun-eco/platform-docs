---
title: "watchShake"
source: "https://open.dingtalk.com/document/development/jsapi-watch-shake"
category: "客户端JSAPI / 基础API / 设备 / 摇一摇"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-watch-shake_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-watch-shake_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用watchShake，启动摇一摇。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11670) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11670) |

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
| frequency | Number | 是 | 150 | 采样间隔(毫秒)，指每隔多长时间对加速度进行一次采样， 然后对比前后变化，判断是否触发shake。 |
| sensitivity | Number | 是 | 20 | 振动幅度，加速度变化超过这个值后触发shake。 |
| callbackDelay | Number | 是 | 3000 | 触发『摇一摇』后的等待时间(毫秒)，防止频繁调用。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.watchShake({
  frequency: 150,
  sensitivity: 20,
  callbackDelay: 3000,
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```