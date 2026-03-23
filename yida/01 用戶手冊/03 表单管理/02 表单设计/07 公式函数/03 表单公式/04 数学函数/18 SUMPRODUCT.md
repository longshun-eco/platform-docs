---
title: "SUMPRODUCT"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/nn2gzi/zrgy7twy6d9ry6ey"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 数学函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**SUMPRODUCT**函数用于执行数组计算并返回乘积之和。此函数可以同时进行多个数组的对应元素相乘，并将所有乘积求和。

## 支持产品场景

SUMPRODUCT函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）
-   集成自动化
-   流程-节点
-   连接器

## 格式

```
SUMPRODUCT(array1,array2...array5)
```

## 属性说明

| 属性 | 是否必填 | 说明 |
| --- | --- | --- |
| array | 是 | 数组类型。需要参与计算的单个或多个数组、范围或引用。多个数组之间使用英文逗号分隔。
**说明**： 参数数组的元素个数必须保持一致。

 |

## 返回值

| 返回值类型 | 说明 |
| --- | --- |
| 双精度浮点数（Double） | 乘法运算后返回的结果。 |

## 使用示例

如下图所示，使用`SUMPRODUCT()`函数计算采购单总额。

![[yida_support-wtwabe-cnzrgo-gvtpe4-nn2gzi-zrgy7twy6d9ry6ey_1704347257035-ff40a4b7-0a32-47a2-9289-d27f94604a5f.gif]]

## 体验

在给定的数组中，将数组间对应的元素相乘，并返回乘积之和，[点击体验效果](https://www.aliwork.com/o/qewesddf?ddtab=true)。
