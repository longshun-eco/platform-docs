---
title: "chooseOneDayInCalendar"
source: "https://open.dingtalk.com/document/development/jsapi-choose-one-day-in-calendar"
category: "客户端JSAPI / 基础API / 界面 / 选择日期"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-one-day-in-calendar_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-one-day-in-calendar_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用chooseOneDayInCalendar，选择某天。

> 选择固定的某天。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11713) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11713) |

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
| default | Number | 是 | 1494415396228 | 时间戳，默认选中日期，单位为毫秒。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| chosen | Number | 1580796000000 | 时间戳，用户选择的日期时间，单位为毫秒。 |
| timezone | Number | 8 | 整型，用户当前所在时区，例如8为第八时区。 |

## **示例****代码**

### 默认出入参

```javascript
dd.chooseOneDayInCalendar({
  default: 1494415396228,
  success: (res) => {
    const { chosen, timezone } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "chosen": 1580796000000, "timezone": 8 }
```