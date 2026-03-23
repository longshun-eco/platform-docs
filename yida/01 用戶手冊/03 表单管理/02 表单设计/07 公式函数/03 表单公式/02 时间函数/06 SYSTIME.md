---
title: "SYSTIME"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/dh7m8n/enkgisafnaalmkl0"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 时间函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**SYSTIME**函数用于获取当前系统时间。

**说明**：

即使客户端的时间被人为调整了，SYSTIME 函数不受影响，获取的仍然是服务器时间。例如签到、打卡等场景下，可避免调整时间作弊的情况。

## 支持产品场景

SYSTIME函数支持在宜搭的以下场景中使用。

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
SYSTIME()
```

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 日期对象 | 返回当前系统时间的时间对象。 |

## 使用示例

如下图所示，你可以使用`SYSTIME()`函数将当前系统时间赋值给**日期组件**。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-enkgisafnaalmkl0_1703066157552-e217742b-cccd-4c66-b41c-43e39d90d75f.png]]

## 体验

返回当前时间，与SYSTIME函数效果相同，[点击体验效果](https://www.aliwork.com/o/wewdv?ddtab=true)。
