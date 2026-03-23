---
title: "MID"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/wcguece1v2ok8b00/pghawu8hdwng91in"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 文本函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**MID**函数用于从指定位置开始截取目标文本指定长度的字符。

## 支持产品场景

MID函数支持在宜搭的以下场景中使用。

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
MID("text",start_index,length)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| text | 是 | 需要截取的原始文本。 |
| start\_index | 是 | 截取文本开始位置，数字类型。 |
| length | 是 | 需要截取文本的字符数，数字类型。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 截取后的文本内容。 |

## 使用示例

下图中公式的执行结果为：`低代码`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-pghawu8hdwng91in_1702885683885-b11d8ac7-95dd-43bf-a53c-2058c6df8b9f.png]]

## 体验

截取文本的有效部分内容，[**点击体验效果**](https://www.aliwork.com/o/sdfyj?ddtab=true)。
