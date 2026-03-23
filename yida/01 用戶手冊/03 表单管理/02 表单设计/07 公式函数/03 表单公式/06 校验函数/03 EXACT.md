---
title: "EXACT"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/kgv5kulzygfhtkoo/onabfl769bhounig"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 校验函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**EXACT**函数用于比较两个字符串是否完全相同（区分大小写）。

## 支持产品场景

EXACT函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   集成自动化
-   流程-节点
-   连接器

## 格式

```
EXACT(value1,value2)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| value1 | 是 | 进行比较的字符串。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔值 | 比较后的结果。
-   **true**：完全相同。
-   **false**：不同。

 |

## 使用示例

如下图所示，使用`EXACT()`函数判断用户输入的值是否为`杭州`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-kgv5kulzygfhtkoo-onabfl769bhounig_1703842684663-8a62a2f5-df12-470d-8ab3-c343ef8f3b3c.png]]

## 体验

判断两个字符串完全相同则返回 true，否则返回 false，[点击体验效果](https://www.aliwork.com/o/weddfsgfrgtrf?ddtab=true)。
