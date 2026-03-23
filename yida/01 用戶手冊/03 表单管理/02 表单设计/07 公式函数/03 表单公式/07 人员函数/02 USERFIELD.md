---
title: "USERFIELD"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/namr73vcz90gduud/oyuexdmpaxiys2tm"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 人員函數"
updated: 
tags:
  - yida
  - 用戶手冊
---

**USERFIELD**函数用于获取指定成员组件中，选中的员工信息。

## 支持产品场景

USERFIELD函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）

## 格式

```
USERFIELD(成员组件,field)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| 成员组件 | 是 | 需要获取信息的成员组件字段。 不支持成员组件多选模式，否则只能获取第一个选中的成员信息。 |
| field | 是 | 需要获取的用户信息类型，取值：
-   **name**：用户名。
-   **userId**：员工的userId，该ID是员工在当前组织的唯一ID，由系统自动生成。
-   **businessWorkNo**：员工工号，可以由管理员指定。

 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 返回的人员信息。 |

## 使用示例

如下图所示，使用`USERFIELD()`函数获取当前登录人的用户名、工号、userId。

![[yida_support-wtwabe-cnzrgo-gvtpe4-namr73vcz90gduud-oyuexdmpaxiys2tm_1704440155958-b46dfc17-02e0-4ba3-849b-9f373a9b1348.gif]]
