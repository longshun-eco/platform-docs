---
title: "NETWORKDAYS"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/dh7m8n/qfwh5ivncnfg57wt"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 时间函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**NETWORKDAYS**函数用于计算两个日期之间有多少个工作日。

## 支持产品场景

NETWORKDAYS函数支持在宜搭的以下场景中使用。

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
WORKDAY(start_time,end_time,holidays)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| start\_time | 是 | 开始时间的时间戳，可以直接使用日期组件的值。 |
| end\_time | 是 | 结束时间的时间戳，可以直接使用日期组件的值。
开始时间和结束时间相隔不得超过50,000天，超过返回空。

 |
| holidays | 否 | 计算排除的日期，日期格式为：`yyyy-MM-dd`。可以设置多个，多个日期之间用英文逗号分隔。

例如：可以将各种省、市、自治区、国家/地区的法定假日及非法定假日。

 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数值 | 返回的工作日的时长。 |

## 使用示例

如下图所示，你可以使用`NETWORKDAYS()`函数计算两个日期之间有多少个工作日。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-qfwh5ivncnfg57wt_1703471746044-16e8ba1d-db8e-4b25-8ccb-f996a1c0ead5.gif]]
