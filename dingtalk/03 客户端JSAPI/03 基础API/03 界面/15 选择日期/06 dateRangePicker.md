---
title: "dateRangePicker"
source: "https://open.dingtalk.com/document/development/jsapi-date-range-picker"
category: "客户端JSAPI / 基础API / 界面 / 选择日期"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-date-range-picker_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-date-range-picker_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用dateRangePicker，选择日期区间。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11707) |
| 小程序 | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |

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
| defaultEnd | Number | 是 | 1780796000000 | 时间戳，默认选中的截止时间，单位为毫秒。 |
| defaultStart | Number | 否 | 1580796000000 | 时间戳，默认选中的开始时间，单位为毫秒。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| end | Number | 1780796000000 | 时间戳，为截止当日0点的时间，单位为毫秒。 |
| start | Number | 1580796000000 | 时间戳，为起始当日0点的时间，单位为毫秒。 |
| timezone | Number | 8 | 整型，用户当前所在时区，例如8为第八时区。 |

## **示例****代码**

### 默认出入参

```javascript
dd.dateRangePicker({
  defaultEnd: 1780796000000,
  defaultStart: 1580796000000,
  success: (res) => {
    const { end, start, timezone } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "end": 1780796000000, "start": 1580796000000, "timezone": 8 }
```