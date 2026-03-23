---
title: "createAnimation"
source: "https://open.dingtalk.com/document/development/jsapi-create-animation"
category: "客户端JSAPI / 基础API / 界面 / 动画"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-create-animation_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-create-animation_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用createAnimation，创建动画实例。调用实例的方法来描述动画，最后通过动画实例的export方法将动画数据导出并传递给组件的animation属性。

### 动画实例方法

动画实例可以调用以下方法来描述动画，调用结束后会返回实例本身，支持链式调用的写法。

#### 样式

| 方法 | 参数 | 说明 |
| --- | --- | --- |
| opacity | value | 透明度，参数范围 0~1。 |
| backgroundColor | color | 颜色值。 |
| width | length | 长度值，如果传入数字则默认单位为 px ，可传入其他自定义单位的长度值。 |
| height | length | 同上。 |
| top | length | 同上。 |
| left | length | 同上。 |
| bottom | length | 同上。 |
| right | length | 同上。 |

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10079) |

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
| duration | Number | 是 |  | 动画的持续时间，单位 ms。  **默认值**：400。 |
| timeFunction | String | 是 |  | 定义动画的效果，有效值："linear"，"ease"，"ease-in"，"ease-in-out"，ease-out"，"step-start"，"step-end"。  **默认值**："linear"。 |
| delay | Number | 是 |  | 动画延迟时间，单位 ms。  **默认值**：0。 |
| transformOrigin | String | 是 |  | 设置transform-origin。  **默认值**："50"。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.createAnimation({
  delay: 69,
  duration: 87,
  timeFunction: `timeFunction示例值`,
  transformOrigin: `transformOrigin示例值`,
});
```