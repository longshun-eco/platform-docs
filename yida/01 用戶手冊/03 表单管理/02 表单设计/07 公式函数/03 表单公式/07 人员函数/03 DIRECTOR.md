---
title: "DIRECTOR"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/namr73vcz90gduud/pvw37ge84kxg9x28"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 人员函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**DIRECTOR** 函数用于获取当前登录成员主管的userId。

## 支持产品场景

DIRECTOR函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）

## 格式

```javascript
DIRECTOR(level)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| level | 是 | 数字类型，获取第几级主管的userId。 传入`1`则返回一级主管，传入`2`则返回二级主管。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 返回的当前登录员工的主管信息。 |

## 使用示例

如下图所示，使用`DIRECTOR()`函数获取当前登录人用户一级主管的userId。

![[yida_support-wtwabe-cnzrgo-gvtpe4-namr73vcz90gduud-pvw37ge84kxg9x28_1704447454536-a2a5d87f-579f-426c-9528-a8b1a363587c.gif]]
