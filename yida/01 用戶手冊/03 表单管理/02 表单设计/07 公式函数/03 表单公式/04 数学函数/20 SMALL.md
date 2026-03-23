---
title: "SMALL"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/nn2gzi/kruy97m10v8mt3mt"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 数学函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**SMALL**函数用于数据集中，第N个最小值。

## 支持产品场景

SMALL函数支持在宜搭的以下场景中使用。

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
SMALL(Array,number)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| Array | 是 | 数组类型的数据。你可以直接使用子表单中的数值组件。 |
| number | 是 | 数字类型，需要获取的第几小的值。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数值 | 最终获取到的值。 |

## 使用示例

如下图所示，使用`SMALL()和ADD()`函数计算全班倒数第二名同学的成绩。

![[yida_support-wtwabe-cnzrgo-gvtpe4-nn2gzi-kruy97m10v8mt3mt_1704248872131-6484d68c-b8d4-4ff1-bb0c-41de69756946.gif]]

## 体验

在子表单多条明细数据中，返回值第 3 小的数据，[点击体验效果](https://www.aliwork.com/o/ssxsd?ddtab=true)。
