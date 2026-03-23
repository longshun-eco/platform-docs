---
title: "SEARCH"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/wcguece1v2ok8b00/mhwnrwy04c03o2z4"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 文本函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

SEARCH函数用于查找目标子文本在母文本中的位置，如果没有找到则返回0。

## 支持产品场景

SEARCH函数支持在宜搭的以下场景中使用。

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
SEARCH(findtext,withintext,start_num)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| findtext | 是 | 被查询的目标子文本内容。 |
| withintext | 是 | 查询的母文本内容（源文本）。 |
| start\_num | 否 | 查询的开始位置，数字类型。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 子文本在母文本中的开始位置。如果没有查到，则返回0。 |

## 使用示例

下图中公式的执行结果为：`3`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-mhwnrwy04c03o2z4_1702973682984-7fc2ce1f-354d-4194-b73e-60344c237b56.png]]

## 体验

查找**单行文本 1** 的内容在 **单行文本 2** 中的位置，[点击体验效果](https://www.aliwork.com/o/qwerwes?ddtab=true)。
