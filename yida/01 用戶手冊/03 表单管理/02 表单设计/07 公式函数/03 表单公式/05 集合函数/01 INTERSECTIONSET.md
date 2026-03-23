---
title: "INTERSECTIONSET"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/pggdxo6349mdy0oi/ah8b9z"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 集合函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**INTERSECTIONSET**函数用于获取两个集合的交集。

## 支持产品场景

INTERSECTIONSET函数支持在宜搭的以下场景中使用。

-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）
-   集成自动化
-   流程-节点
-   连接器

## 格式

```
INTERSECTIONSET(arrayA,arrayB)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| arrayA | 是 | 需要计算交集的集合，多个集合之间使用英文逗号分隔。**说明**：- 目前仅支持计算成员组件的交集。- 不支持在子表单中使用。 |
| arrayB | 是 |  |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数组 | 成员的userid列表。 |

## 使用示例

如下图所示，使用`INTERSECTIONSET()`和`EMPLOYEE()`函数计算两个成员组件的交集。

![[yida_support-wtwabe-cnzrgo-gvtpe4-pggdxo6349mdy0oi-ah8b9z_1704361486988-504f5612-1766-43f2-b20f-c9228bd2436e.gif]]
