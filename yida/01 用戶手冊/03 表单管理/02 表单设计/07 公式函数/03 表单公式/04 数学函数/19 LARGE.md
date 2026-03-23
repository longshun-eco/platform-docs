---
title: "LARGE"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/nn2gzi/rnyume8c4kkywdpg"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 数学函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**LARGE**函数用于数据集中，第N个最大值。

## 支持产品场景

LARGE函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）
-   集成自动化
-   流程-节点
-   连接器

## 格式

```javascript
LARGE(Array,number)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| Array | 是 | 数组类型的数据。你可以直接使用子表单中的数值组件。 |
| number | 是 | 数字类型，需要获取的第几大的值。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数值 | 最终获取到的值。 |

## 使用示例

如下图所示，使用`LARGE()`函数计算子表单数学成绩第二的成绩。

![[yida_support-wtwabe-cnzrgo-gvtpe4-nn2gzi-rnyume8c4kkywdpg_1704352203812-e23b3744-04d6-4618-8204-937c742f096c.png]]

## 体验

在子表单多条明细数据（数字型数据）中，返回值第 3 大的数据，[点击体验效果](https://www.aliwork.com/o/wrtff?ddtab=true)。
