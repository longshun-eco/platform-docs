---
title: "TIMECOMPARE"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/mnx96u/orqe469rrf2yn6gr"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 逻辑函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**TIMECOMPARE** 函数用于比较两个日期的大小。

## 支持产品场景

TIMECOMPARE 函数支持在宜搭的以下场景中使用。

- 表单（主表字段）
- 表单（业务关联规则）
- 表单（校验）
- 流程设计（校验规则）
- 集成自动化
- 流程-节点
- 连接器

## 格式

```
TIMECOMPARE(end_time,start_time)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| start_time | 是 | 需要进行比较的时间戳，可直接使用日期选择框。 |
| end_time | 是 |  |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 布尔值 | 两个时间比较的结果，取值：
- **true**：表示 **start_time** 大于 **end_time**。
- **false**：表示 **start_time** 小于等于 **end_time**。

 |

## 使用示例

如下图所示，你可以使用 `TIMECOMPARE()` 函数对两个日期组件的值进行比较。

![[yida_support-wtwabe-cnzrgo-gvtpe4-mnx96u-orqe469rrf2yn6gr_1703234953551-b4827699-9d3e-4382-8ea2-0bb6003ab638.png]]

## 体验

比较两个时间的大小，**日期1** 大于 **日期2** 返回 **true**，否则返回 **false** ，[点击体验效果](https://www.aliwork.com/o/dfrfrf?ddtab=true)。
