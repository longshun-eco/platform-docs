---
title: "TEXT"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/wcguece1v2ok8b00/bt0wov266h45hpi4"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 文本函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

TEXT函数用于将数字格式化成指定格式文本。

## 支持产品场景

TEXT函数支持在宜搭的以下场景中使用。

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
TEXT(num, pattern)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| num | 是 | 需要进行格式化转换的数字。 |
| pattern | 是 | 指定格式。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 格式化完成后的内容。 |

## 使用示例

-   格式化普通数字内容：

下图中公式的执行结果为：`1,234,567,890`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-bt0wov266h45hpi4_1702978848279-48cea931-5b7f-4934-ad16-2c877f27bb1d.png]]

-   格式化时间内容：

下图中公式的执行结果为：`2023-12-19 17:26:07`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-bt0wov266h45hpi4_1702979053646-63b29572-68f5-4aed-82e0-40e52ea579d5.png]]

## 体验

将数字格式化成指定格式文本，[点击体验效果](https://www.aliwork.com/o/qqdd?ddtab=true)。
