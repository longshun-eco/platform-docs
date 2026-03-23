---
title: "SUBSET"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/pggdxo6349mdy0oi/ad122fe2ufqbog42"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 集合函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**SUBSET** 函数用于计算集合B是不是集合A的子集。

## 支持产品场景

SUBSET函数支持在宜搭的以下场景中使用。

-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）
-   集成自动化
-   流程-节点
-   连接器

## 格式

```javascript
SUBSET(arrayA,arrayB)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| arrayA | 是 | 需要进行计算的集合，
**说明**：

-   仅支持**成员**和**多选**组件。
-   不支持在子表单中使用。

 |
| arrayB | 是 |  |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔类型 | 集合B是否为集合A的子集，取值：
-   **true**：表示集合B是集合A的子集。
-   **false**：表示集合B不是集合A的子集。

 |

## 使用示例

如下图所示，当成员B是成员A的子集时，阻断表单提交。

![[yida_support-wtwabe-cnzrgo-gvtpe4-pggdxo6349mdy0oi-ad122fe2ufqbog42_1704365593721-202f1c7a-159e-4ff6-9671-3644ae042795.gif]]

## 体验

当复选框2时复选框1的子集时，阻断表单提交，[点击立即体验](https://www.aliwork.com/o/subset)。
