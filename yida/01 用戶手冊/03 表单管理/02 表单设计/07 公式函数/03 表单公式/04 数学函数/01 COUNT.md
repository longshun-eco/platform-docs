---
title: "COUNT"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/nn2gzi/ygcgwobc4tewnmxr"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 数学函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**COUNT**函数用于统计指定表单提交的数据总数。

**说明：**

本函数暂不支持进行逻辑运算。

## 支持产品场景

COUNT函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）
-   流程-节点
-   连接器

## 格式

```
COUNT(formuuid)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| formuuid | 是 | 表单的唯一标识。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 日期对象 | 返回当前表单的总数量。 |

## 使用示例

如下图所示，你可以使用`COUNT()`函数获取当前表单的总数据量，参数值可以为表单ID或流水号组件。

![[yida_support-wtwabe-cnzrgo-gvtpe4-nn2gzi-ygcgwobc4tewnmxr_1704179979924-b8ae3677-9cc2-4755-9111-2c5eae50c76f.png]]

## 体验

统计指定表单提交的数据总数，[点击体验效果](https://www.aliwork.com/o/tyuurr?ddtab=true)。
