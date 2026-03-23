---
title: "DAYEND"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/dh7m8n/me7p9i2f32erci85"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 时间函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**DAYEND**函数用于将指定日期的时分秒设置为一天中的最后时间，即`23:59:59`。

## 支持产品场景

DAYEND函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）
-   集成自动化
-   流程-节点
-   连接器

## 格式

```javascript
DAYEND(timestamp)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| timestamp | 是 | 需要设置的日期的时间戳，可以直接使用日期组件。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| timestamp | 修改后的日期时间戳，可以直接赋值给日期组件。 |

## 使用示例

如下图所示，你可以使用`DAYEND()`函数将指定日期的时分秒设置为`23:59:59`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-me7p9i2f32erci85_1703215310426-bd3d04f6-30eb-46b2-b78c-aff0dcdba6af.png]]

## 体验

将指定日期组件的时间戳的时分秒置零后的时间戳结果，[点击体验效果](https://www.aliwork.com/o/qwqwzz?ddtab=true)。
