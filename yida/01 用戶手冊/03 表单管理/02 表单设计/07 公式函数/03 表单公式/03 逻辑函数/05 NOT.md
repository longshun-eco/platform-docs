---
title: "NOT"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/mnx96u/rzixdcx24zsd1ldx"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 逻辑函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**NOT**函数表示非，可以获取某个逻辑值的相反值。

## 支持产品场景

NOT函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   集成自动化
-   流程-节点
-   连接器

## 格式

```
NOT(logical)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| logical | 是 | 需要计算相反值的逻辑值，true或false。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔值 | 某个逻辑值的相反值。 |

## 使用示例

如下图所示，你可以将`NOT()`和`NE()`函数结合，判断某人年龄是否等于30。

![[yida_support-wtwabe-cnzrgo-gvtpe4-mnx96u-rzixdcx24zsd1ldx_1703830710539-7a049461-15f4-4cd0-8a4b-a86a5d9e9a69.gif]]

## 体验

数值组件小于 0 阻断提交，[点击体验效果](https://www.aliwork.com/o/eryuff?ddtab=true)。
