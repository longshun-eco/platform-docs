---
title: "DEPTNAME"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/namr73vcz90gduud/igrvxuztr0syw9sn"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 人员函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**DEPTNAME**函数用于根据userId获取指定用户所在的部门信息。

## 支持产品场景

DEPTNAME函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）

## 格式

```
DEPTNAME(userid)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| userId | 否 | 需要查询的用户userId。 该userId可以使用成员组件进行获取。如果获取当前登录用户的部门可以直接使用`LOGINUSERWORKNO()`函数获取。 例如：`DEPTNAME(LOGINUSERWORKNO())` |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 返回的当前登录员工的部门名称。 |

## 使用示例

如下图所示，使用`DEPTNAME()`和`LOGINUSERWORKNO()`函数获取当前登录员工所在的部门名称。

![[yida_support-wtwabe-cnzrgo-gvtpe4-namr73vcz90gduud-igrvxuztr0syw9sn_1704448696419-313e9d39-03fa-4a32-b87e-061b73a223b0.gif]]
