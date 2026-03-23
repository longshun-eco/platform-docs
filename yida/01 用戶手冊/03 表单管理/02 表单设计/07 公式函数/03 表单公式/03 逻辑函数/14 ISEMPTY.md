---
title: "ISEMPTY"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/mnx96u/gf7g82pavtbc4y5g"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 逻辑函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**ISEMPTY**函数用于判断某组件的值是否空文本、空对象或者空数组，如果为空则返回true，不为空则返回false。

## 支持产品场景

ISEMPTY函数支持在宜搭的以下场景中使用。

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
ISEMPTY(value1)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| value1 | 是 | 需要进行判断的值。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔值 | 两个参数比较后的结果，取值。
-   **true**：如果返回true，表示为空。
-   **false**：如果返回false，表示不为空。

 |

## 使用示例

如下图所示，使用`ISEMPTY()`函数判断日期组件是否为空。

![[yida_support-wtwabe-cnzrgo-gvtpe4-mnx96u-gf7g82pavtbc4y5g_1703752268842-61005db8-412a-4bfb-aa19-b9c8698712b7.png]]

## 体验

提交的组件值是空值就阻断提交表单，[点击体验效果](https://www.aliwork.com/o/wwty?ddtab=true)。
