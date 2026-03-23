---
title: "EXIST"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/kgv5kulzygfhtkoo/vs0ddo8m5ggofmtb"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 校验函数"
updated: 
tags:
  - yida
  - 用戶手冊
---
**EXIST**函数用于判断当前提交数据是否与历史数据重复。

## 支持产品场景

EXIST函数支持在宜搭的以下场景中使用。

-   表单（校验）
-   流程设计（校验规则）

**说明：**

-   EXIST 暂不支持子表单内的组件验重。
-   EXIST 验重时，需要确保每个组件都有值，只要有一个组件为空，系统默认该条记录不重复。
-   EXIST 当前支持的组件: **单行文本**、**多行文本**、**数值**、**单选**、**下拉单选**、**复选**、**下拉复选**、**级联选择**、**日期**、**日期区间**、**成员**、**国家**、**部门**。

## 格式

```
EXIST(value1,value2···value5)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| value1 | 是 | 需要判断的组件字段。 支持判断多个组件的值，多个组件之间使用英文逗号分隔，最多支持 5 个。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔值 | 比较后的结果。
-   **true**：重复。
-   **false**：不重复。

 |

## 使用示例

如下图所示，使用`EXIST()`函数查找某字段是否已经存在。

![[yida_support-wtwabe-cnzrgo-gvtpe4-kgv5kulzygfhtkoo-vs0ddo8m5ggofmtb_1703841192766-61282671-2a38-450f-a5d7-a2051a86d394.gif]]

## 体验

校验字段值或者联合字段值，是否已经在数据库中存在，[点击体验效果](https://www.aliwork.com/o/2234settt?ddtab=true)。
