---
title: "HASEMPTYTEXT"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/mnx96u/klvwx6gxfw6g6fgs"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 逻辑函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**HASEMPTYTEXT**函数用于检查用户输入、文件内容或者子表单中是否包含空字符串。

## 支持产品场景

HASEMPTYTEXT函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（子表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）
-   集成自动化
-   流程-节点
-   连接器

## 格式

```
HASEMPTYTEXT(value1)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| value1 | 是 | 需要判断的某个文本框、文件、子表单列等。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔值 | 是否包含空字符串，取值：
-   **true**：包含。
-   **false**：不包含。

 |

## 使用示例

如下图所示，`HASEMPTYTEXT()`函数可以判断输入框中是否为空。

![[yida_support-wtwabe-cnzrgo-gvtpe4-mnx96u-klvwx6gxfw6g6fgs_1703582550057-2696ff7b-55ae-4114-89d6-24aac5a9496f.gif]]

## 体验

你可以在以下示例中体验`HASEMPTYTEXT()`函数，[点击体验效果](https://www.aliwork.com/o/22wsdf?ddtab=true)。
