---
title: "XOR"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/mnx96u/evp4gkq8kcv4hgga"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 逻辑函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**XOR**函数表示异或。

XOR用于比较逻辑表达式，该函数仅在如下情况下为真（true）。

-   当且仅有一个逻辑表达式为真（true），其他逻辑表达式为假（false）时，整个XOR函数的值为真（true）。

## 支持产品场景

XOR函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   集成自动化
-   流程-节点
-   连接器

## 格式

```
XOR(condition1,condition2....condition.N)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| condition1 | 是 | 需要评估的逻辑表达式或条件。
-   当且仅有一个逻辑表达式为真（true），其他逻辑表达式为假（false）时，整个XOR函数的值为真（true）。

 |
| condition2 | 是 |  |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔值 | 函数的返回值。 |

## 使用示例

如下图所示，只有`数值 1`的值大于 2，`数值 2`的值小于等于2时，`XOR()`函数才为**true**。

![[yida_support-wtwabe-cnzrgo-gvtpe4-mnx96u-evp4gkq8kcv4hgga_1703571961580-0d8f8d04-2eb0-4300-a04f-e2fa6aaf461e.gif]]
