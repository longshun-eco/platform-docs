---
title: "IntersectionObserver.observe"
source: "https://open.dingtalk.com/document/development/jsapi-intersection-observer-observe"
category: "客户端JSAPI / 基础API / 界面 / 节点查询"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-intersection-observer-observe_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-intersection-observer-observe_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用IntersectionObserver.observe，指定目标节点并开始监听相交状态变化情况。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10037) |

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
| targetSelector | String | 是 | xxId | 选择器。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| time | Number | 1677725294970 | 相交检测时的时间戳。 |
| relativeRect | Object |  | 参照区域的边界。 |
| intersectionRect | Object |  | 相交区域的边界。 |
| intersectionRatio | Number | 0.5 | 相交比例。 |
| boundingClientRect | Object |  | 目标边界。 |

## **示例****代码**

### 默认出入参

```javascript
const intersectionObserver = dd.IntersectionObserver();

intersectionObserver.observe('xxId', (res) => {
  const {
    time,
    relativeRect,
    intersectionRect,
    intersectionRatio,
    boundingClientRect,
  } = res;
});
```

`callback`返回对象示例：

```json
{
  "time": 1677725294970,
  "relativeRect": { "top": 50, "left": 0, "right": 100, "bottom": 200 },
  "intersectionRect": { "top": 50, "left": 0, "right": 100, "bottom": 200 },
  "intersectionRatio": 0.5,
  "boundingClientRect": { "top": 50, "left": 0, "right": 100, "bottom": 200 }
}
```