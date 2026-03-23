---
title: "CEILING"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/nn2gzi/pfdukipqlw5rko8s"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 数学函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

CEILING函数用于将数字向上舍入到最接近的整数或最接近的指定基数的倍数。

## 支持产品场景

ROUND函数支持在宜搭的以下场景中使用。

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
CEILING(number,significance)
```

## 属性说明

| 属性 | 是否必填 | 说明 |
| --- | --- | --- |
| number | 是 | 数字类型，需要进行舍入的数字。 |
| significance | 是 | 指定基数（倍数）。 |

## 返回值

| 返回值类型 | 说明 |
| --- | --- |
| 数值 | 舍入后的值。 |

## 使用示例

如下图所示，使用`CEILING()`函数将某个数进行向上取整操作。

![[yida_support-wtwabe-cnzrgo-gvtpe4-nn2gzi-pfdukipqlw5rko8s_1704265961122-aeddbf37-ee61-47f1-8540-0009a4687a34.png]]

## 体验

向上舍入（沿绝对值增大的方向）为最接近的指定基数的3倍数，[点击体验效果](https://www.aliwork.com/o/wqss?ddtab=true)。
