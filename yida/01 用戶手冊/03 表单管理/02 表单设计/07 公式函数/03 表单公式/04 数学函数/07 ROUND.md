---
title: "ROUND"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/nn2gzi/gzx4fgcgya1g7dzv"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 数学函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

ROUND函数用于将某个数值四舍五入到指定小数点位数。

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
ROUND(number,num_digits)
```

## 属性说明

| 属性 | 是否必填 | 说明 |
| --- | --- | --- |
| number | 是 | 数字类型，需要四舍五入的数字。 |
| num\_digits | 是 | 需要保留的小数点位数。 |

## 返回值

| 返回值类型 | 说明 |
| --- | --- |
| 数值 | 四舍五入后的值。 |

## 使用示例

如下图所示，使用`ROUND()`函数获取一个数字保留两位小数点后的值。

![[yida_support-wtwabe-cnzrgo-gvtpe4-nn2gzi-gzx4fgcgya1g7dzv_1704253626328-24c28d56-c4e2-4d8e-868f-9b52d60e6332.png]]

## 体验

数值出现小数点的时候，将小位数指定到对应的位数，[点击体验效果](https://www.aliwork.com/o/2323ser?ddtab=true)。
