---
title: "singleSelect"
source: "https://open.dingtalk.com/document/development/jsapi-single-select"
category: "客户端JSAPI / 基础API / 界面 / 选项选择器"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-single-select_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-single-select_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用singleSelect，进行下拉框单选配置。

![[development-jsapi-single-select_p177833.png]]

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11616) |
| 小程序 | 7.0.10 | 7.0.10 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11616) |

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
| source | Array<Object> | 是 | [{ key: '选项1', //显示文本 value: '123' //值， },{ key: '选项2', value: '234' }] | 下拉控件的内容。 |
| selectedKey | String | 否 | 选项1 | 默认选中的key值。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| key | String |  |  |
| value | String |  |  |

## **示例****代码**

### 默认出入参

```javascript
dd.singleSelect({
  source: [
    {
      key: '选项1', //显示文本
      value: '123', //值，
    },
    {
      key: '选项2',
      value: '234',
    },
  ],
  selectedKey: '选项1',
  success: (res) => {
    const { key, value } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "key": `key示例值`, "value": `value示例值` }
```