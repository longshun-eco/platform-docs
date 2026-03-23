---
title: "EMPLOYEE"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/namr73vcz90gduud/sxc8gv9dkhmt8zro"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 人員函數"
updated: 
tags:
  - yida
  - 用戶手冊
---

**EMPLOYEE**函数用于根据userId数组获取员工信息列表。

## 支持产品场景

EMPLOYEE函数支持在宜搭的以下场景中使用。

-   表单（主表字段）

## 格式

```
EMPLOYEE(array)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| array | 是 | 员工的userId数组。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数组 | 对应的人员信息列表。 |

## 使用示例

-   使用成员组件的userId获取。

如下图所示，使用`EMPLOYEE()`和`UNIONSET()`函数获取多个成员组件的员工信息列表。

![[yida_support-wtwabe-cnzrgo-gvtpe4-namr73vcz90gduud-sxc8gv9dkhmt8zro_1704444493463-ee219061-9367-4a50-a8b0-f1bbaca783f2.gif]]
