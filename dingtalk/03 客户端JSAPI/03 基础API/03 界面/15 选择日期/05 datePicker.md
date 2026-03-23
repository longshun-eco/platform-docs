---
title: "datePicker"
source: "https://open.dingtalk.com/document/development/jsapi-date-picker"
category: "客户端JSAPI / 基础API / 界面 / 选择日期"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-date-picker_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-date-picker_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用dd.datePicker打开日期选择列表。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10077) |
| 小程序 | 6.0.0 | 6.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10077) |

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
| format | String | 否 | yyyy-MM-dd | 返回的日期格式。   * yyyy-MM-dd（默认） * HH:mm * yyyy-MM-dd HH:mm * yyyy-MM |
| currentDate | String | 否 | 2012-12-12 | 初始选择的日期时间。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| date | String | 2012-12-12 | 选择的日期。 |

## **示例****代码**

### 默认出入参

```javascript
dd.datePicker({
  format: 'yyyy-MM-dd',
  currentDate: '2012-12-12',
  success: (res) => {
    const { date } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "date": "2012-12-12" }
```