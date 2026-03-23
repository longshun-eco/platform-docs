---
title: "AND"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/mnx96u/uobzicixvh02io31"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 逻辑函数"
updated: 
tags:
  - yida
  - 用戶手冊
---
**AND**函数表示且或者和。只有函数中所有逻辑表达式都返回true时，AND函数的值才为true，否则返回false。

## 支持产品场景

AND函数支持在宜搭的以下场景中使用。

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
AND(condition1,condition2....condition.N)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| condition1 | 是 | 需要评估的逻辑表达式或条件。 用于判断两个或多个条件是否都为真（即是否都满足特定条件）。
-   如果所有的条件都为真（逻辑值为true），那么AND函数的返回true。
-   如果有任何一个条件为假（逻辑值为false），那么AND函数返回false。

 |
| condition2 | 是 |  |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔值 | 所有逻辑表达式是否都为true。 |

## 使用示例

如下图所示，只有`数值1`和`数值2`的值都大于 2 时，`AND()`函数的返回值才为**true**，否则为**false**。

![[yida_support-wtwabe-cnzrgo-gvtpe4-mnx96u-uobzicixvh02io31_1703494385083-1ffc6cf6-2009-447d-9a8e-18b9b82b22a2.gif]]

## 体验

多个组件同时满足条件就会阻断提交表单，[点击体验效果](https://www.aliwork.com/o/wwoyn?ddtab=true)。
