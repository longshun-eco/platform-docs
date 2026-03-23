---
title: "RIGHT"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/wcguece1v2ok8b00/ch2gvwhzh2bn9u82"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 文本函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**RIGHT**函数用于从文本的最后一个字符开始返回指定个数的字符。如果文本长度小于指定字符的个数，会直接返回原始文本。

## 支持产品场景

RIGHT函数函数支持在宜搭的以下场景中使用。

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
RIGHT(text, num_chars)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| text | 是 | 需要获取右侧字符的文本。 |
| num_chars | 是 | 获取的文本长度。如果长度大于文本总字符数，将直接返回原始文本。 |

## 返回值

| 属性 | 说明 |
| --- | --- |
| text | 从右往左返回的指定个数的文本。 |

## 使用示例

下图中公式的执行结果为：`低代码`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-ch2gvwhzh2bn9u82_1702957024198-4c84b474-8ca9-488d-9e53-e74c20dd5fcf.png]]

## 体验

返回**单行输入框**组件倒数第三个字符到倒数第一个字符值，[点击体验效果](https://www.aliwork.com/o/dsxza?ddtab=true)。
