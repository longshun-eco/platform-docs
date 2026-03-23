---
title: "ARRAYREPEATED"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/kgv5kulzygfhtkoo/fs8ym2"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 校验函数"
updated: 
tags:
  - yida
  - 用戶手冊
---
**ARRAYREPEATED**函数用于判断子表单内组件的值是否重复，仅支持子表单内的字段。

## 支持产品场景

ARRAYREPEATED函数支持在宜搭的以下场景中使用。

-   表单（校验）
-   流程设计（校验规则）

## 格式

```
ARRAYREPEATED(field)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| field | 是 | 子表单内的组件字段。 最终入参数格式类似如下：`["11","11","11"]`。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔值 | 是否有重复字段，取值：
-   **true**：如果返回true，表示有重复的值。
-   **false**：如果返回false，表示没有重复的值。

 |

## 使用示例

如下图所示，使用`ARRAYREPEATED()`子表单某一列中是否有重复的值。

![[yida_support-wtwabe-cnzrgo-gvtpe4-kgv5kulzygfhtkoo-fs8ym2_1703839509018-0951e7fa-959b-4043-83df-3fc798fbb974.gif]]

## 体验

使用ARRAYREPEATED函数判断数组是否重复，[点击体验效果](https://www.aliwork.com/o/3454frty?ddtab=true)
