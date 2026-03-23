---
title: "REPLACE"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/wcguece1v2ok8b00/gtz0638tp96gbnhf"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 文本函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

REPLACE函数用于根据指定的字符数，将部分文本替换为新的文本。

## 支持产品场景

REPLACE函数支持在宜搭的以下场景中使用。

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
REPLACE(oldtext, startnum, numchars, newtext)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| oldtext | 是 | 要替换字符的文本。 |
| startnum | 是 | 被替换的旧文本开始位置。 |
| numchars | 是 | 需要替换的旧文本字符数。 |
| newtext | 是 | 替换旧文本中字符的内容。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 替换后的新文本内容。 |

## 使用示例

下图中公式的执行结果为：`宜搭应用开发平台`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-gtz0638tp96gbnhf_1702892994706-98ef116f-6f07-4d22-9197-2f564efff241.png]]

## 体验

根据指定的字符数，将部分文本字符串替换为不同的文本字符串，[**点击体验效果**](https://www.aliwork.com/o/qqwex?ddtab=true)**。**
