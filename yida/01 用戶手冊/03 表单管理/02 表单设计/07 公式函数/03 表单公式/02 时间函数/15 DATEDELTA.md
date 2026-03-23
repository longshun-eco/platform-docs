---
title: "DATEDELTA"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/dh7m8n/tz0uzryeft12rpgw"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 时间函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**DATEDELTA**函数用于计算增加或减少指定天数后的日期。

## 支持产品场景

DATEDELTA函数支持在宜搭的以下场景中使用。

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
DATEDELTA(date,delta_days)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| date | 是 | 时间对象。 |
| delta\_days | 是 | 需要增加的天数。正数为增加负数为减少。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数字 | 增加或减少指定日期后的时间，时间戳格式。 |

## 使用示例

如下图所示，你可以使用`DATEDELTA()`函数计算 100 天后的日期，并将其赋值给日期组件。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-tz0uzryeft12rpgw_1703157304167-202d8c98-1c45-4b70-a489-0312d218529b.png]]

## 体验

将指定日期增加或减少指定天数，[点击体验效果](https://www.aliwork.com/o/wewers?ddtab=true)。
