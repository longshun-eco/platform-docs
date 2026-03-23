---
title: "WEEKNUM"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/dh7m8n/kn045dietny22f9k"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 时间函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

WEEKNUM 函数获取指定日期是当年的第几周。

## 支持产品场景

WEEKNUM 函数支持在宜搭的以下场景中使用。

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
WEEKNUM(date, return_type)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| date | 是 | 时间对象。 |
| return\_type | 否 | 每周的起始时间。取值：
-   1：表示每周从周日开始
-   2：表示每周从周一开始

默认值为 1。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数字 | 返回日期周数。 |

## 使用示例

如下图所示，你可以使用`WEEKNUM()`函数获取指定日期的周数。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-kn045dietny22f9k_1703166941058-5f5e047e-6a64-4dcb-91b6-722b61ba35ad.png]]

## 体验

返回特定日期的周数。例如，包含 1 月 1 日为该年的第 1 周，其编号为第 1 周，[点击体验效果](https://www.aliwork.com/o/vrrdf?ddtab=true)。
