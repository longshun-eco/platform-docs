---
title: "multiSelect"
source: "https://open.dingtalk.com/document/development/jsapi-multi-select"
category: "客户端JSAPI / 基础API / 界面 / 选项选择器"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-multi-select_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-multi-select_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用multiSelect，进行下拉框多选配置。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11617) |
| 小程序 | 7.0.10 | 7.0.10 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11617) |

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
| options | Array<String> | 是 | ['选项1', '选项2', '选项3', '选项4'] | 待选选项列表。 |
| selectOption | Array<String> | 否 |  | 已选选项列表。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| 出参 | Array<Number> |  |  |

## **示例****代码**

### 默认出入参

```
dd.multiSelect({
  options: ['选项1', '选项2', '选项3', '选项4'],
  selectOption: [`selectOption示例值1`, `selectOption示例值2`],
  success: (res) => {
    // res: [59, 95]
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
[49, 31]
```