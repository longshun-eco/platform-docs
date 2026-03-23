---
title: "FIXED"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/nn2gzi/an1t8blpsi4aue68"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 数学函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**FIXED**函数用于将数字舍入到指定的小数位数，以十进制数格式对该数进行格式设置，并以数字形式返回结果。

## 支持产品场景

FIXED函数支持在宜搭的以下场景中使用。

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
FIXED(number, decimals)
```

## 属性说明

| 属性 | 是否必填 | 说明 |
| --- | --- | --- |
| number | 是 | 数字类型，要进行舍入数字。 |
| decimals | 否 | 数字类型，小数点右边的位数。 |

## 返回值

| 返回值类型 | 说明 |
| --- | --- |
| 数值 | 舍入到指定小数位数。 |

## 使用示例

如下图所示，使用`FIXED()`函数将`3.141592657`保留两位小数。

![[yida_support-wtwabe-cnzrgo-gvtpe4-nn2gzi-an1t8blpsi4aue68_1704284530904-9b9e290e-b9a0-4056-be21-9bd4c017e127.png]]

## 体验

将数字舍入到指定第2个小数位数，[点击体验效果](https://www.aliwork.com/o/wersv?ddtab=true)。
