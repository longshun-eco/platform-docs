---
title: "ISOWEEKNUM"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/dh7m8n/bn3zv56eunro0tzd"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 时间函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**ISOWEEKNUM**函数用于获取指定日期的ISO周数，ISO周数是根据ISO 8601标准计算一年中周的位置。

ISO 8601规定了每周从周一开始，并且每年的第一周是包含公历年第一个周四的那一周。

## 支持产品场景

ISOWEEKNUM函数支持在宜搭的以下场景中使用。

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
ISOWEEKNUM(date)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| date | 是 | 时间对象。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数字 | 返回日期的ISO周数。 |

## 使用示例

如下图所示，你可以使用`ISOWEEKNUM()`函数获取指定日期的周数。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-bn3zv56eunro0tzd_1703210271577-88bdffcd-d601-4535-9aa2-0c8ee744017a.png]]

## 体验

返回一个指定日期在当年的周数 ，[点击体验效果](https://www.aliwork.com/o/swwf?ddtab=true)。
