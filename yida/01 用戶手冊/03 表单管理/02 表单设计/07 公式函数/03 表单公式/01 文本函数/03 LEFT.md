---
title: "LEFT"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/wcguece1v2ok8b00/xylna43s4gpoyz9k"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 文本函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**LEFT** 函数用于从一个文本的第一个字符开始返回指定个数的字符。如果文本长度小于指定字符的个数，会直接返回原始文本。

## 支持产品场景

LEFT 函数支持在宜搭的以下场景中使用。

- 表单（主表字段）
- 表单（业务关联规则）
- 表单（校验）
- 流程设计（校验规则）
- 流程设计（关联操作）
- 集成自动化
- 流程-节点
- 连接器

## 格式

```
LEFT(text, num_chars)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| text | 是 | 需要获取左侧字符的文本。 |
| num_chars | 是 | 获取的文本长度。如果长度大于文本总字符数，将直接返回原始文本。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 从左到右返回的指定个数的文本。 |

## 使用示例

下图中公式的执行结果为：`宜搭`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-xylna43s4gpoyz9k_1702957240444-08839f33-850f-4345-93ac-626481d2430a.png]]

## 体验

返回输入框组件第一个字符到第二个字符值，[点击体验效果](https://www.aliwork.com/o/wuwwuwu?ddtab=true)。
