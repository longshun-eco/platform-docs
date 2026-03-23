---
title: "ISNULL"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/mnx96u/zia9xssidpga5tqx"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 逻辑函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**ISNULL**函数用于判断某组件是否为NULL，如果为NULL则返回true，不为NULL则返回false。

## 支持产品场景

ISNULL函数支持在宜搭的以下场景中使用。

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
ISNULL(value1)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| value1 | 是 | 需要进行判断的值。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔值 | 两个参数比较后的结果，取值。
-   **true**：如果返回true，表示不为NULL。
-   **false**：如果返回false，表示为NULL。

 |

## 使用示例

如下图所示，使用`ISNULL()`函数判断附件组件是否为NULL。

![[yida_support-wtwabe-cnzrgo-gvtpe4-mnx96u-zia9xssidpga5tqx_1703820135351-be4f1566-f1b6-4f74-9f43-6941062fec3c.png]]
