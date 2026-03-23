---
title: "TIMESTAMP"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/dh7m8n/bmgm5sirz825ncal"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 时间函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**TIMESTAMP**函数用于将日期对象转换为时间戳，你可以将该时间戳赋值给日期组件。

## 支持产品场景

TIMESTAMP函数支持在宜搭的以下场景中使用。

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
TIMESTAMP(date)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| date | 是 | 日期对象。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 时间戳 | 转换后的数值。
**说明**： 日期对象可以理解为年月日时分秒。日期对象的格式为 `Sat Aug 01 2015 00:00:00 GMT+0800（中国标准时间）`，即北京时间 2015 年 8 月 1 日 00:00:00。日期对象可以进行各种运算，比如日期加减法等。

 |

## 使用示例

如下图所示，你可以使用TIMESTAMP()函数将当前时间的时间戳赋值到日期组件。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-bmgm5sirz825ncal_1703059876598-01bf249b-52c5-481f-9b6d-a06e190f571b.png]]

## 体验

将日期对象转换成时间戳，主要用来将日期公式计算出的日期对象转为时间戳，给日期组件赋值，[点击体验效果](https://www.aliwork.com/o/ssdefer?ddtab=true)。
