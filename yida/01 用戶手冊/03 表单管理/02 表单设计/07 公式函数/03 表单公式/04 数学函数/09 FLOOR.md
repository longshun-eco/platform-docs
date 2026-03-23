---
title: "FLOOR"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/nn2gzi/gkzdswxg4g18443y"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 数学函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

FLOOR函数用于将数字向下舍入到最接近的整数或最接近的指定基数的倍数。

## 支持产品场景

FLOOR函数支持在宜搭的以下场景中使用。

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
FLOOR(number,significance)
```

## 属性说明

| 属性 | 是否必填 | 说明 |
| --- | --- | --- |
| number | 是 | 数字类型，需要进行向下舍去的数字。 |
| significance | 是 | 指定基数（倍数）。 |

## 返回值

| 返回值类型 | 说明 |
| --- | --- |
| 数值 | 舍去后的值。 |

## 使用示例

如下图所示，使用`FLOOR()`函数将某个数进行向下取整操作。

![[yida_support-wtwabe-cnzrgo-gvtpe4-nn2gzi-gkzdswxg4g18443y_1704266295688-e0cd5be7-c402-46d6-b4e3-60fca99c29bb.png]]

## 体验

向下舍入（沿绝对值增大的方向）为最接近的指定基数的3倍数，[点击体验效果](https://www.aliwork.com/o/wwewd?ddtab=true)。
