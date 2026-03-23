---
title: "TIME"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/dh7m8n/zl268y77wk9nhwkg"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 时间函数"
updated: 
tags:
  - yida
  - 用戶手冊
---
**TIME**函数用于将指定时间的时间戳转换为十进制的时间。

## 支持产品场景

TIME函数支持在宜搭的以下场景中使用。

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
TIME(hour,minute,second)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| hour | 是 | 时间戳，小时。 |
| minute | 是 | 时间戳，分钟。 |
| second | 是 | 时间戳，秒。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数字 | 返回特定时间的十进制数字。时间值为日期值的一部分，并用十进制数表示。 |

## 使用示例

如下图所示，你可以使用TIME()函数将当前时间的时间戳转换为十进制数字。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-zl268y77wk9nhwkg_1703062959806-8b9fe4f7-4259-459e-9a81-215c969fb738.png]]

## 体验

返回特定时间的十进制数字。时间值为日期值的一部分，并用十进制数表示，[点击体验效果](https://www.aliwork.com/o/ssewd?ddtab=true)。
