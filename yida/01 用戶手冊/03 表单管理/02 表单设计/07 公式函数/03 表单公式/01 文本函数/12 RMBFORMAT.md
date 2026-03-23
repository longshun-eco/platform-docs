---
title: "RMBFORMAT"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/wcguece1v2ok8b00/ff4mghegi9kbsc7m"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 文本函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**RMBFORMAT** 函数用于将数值格式化为大写的人名币格式。

## 支持产品场景

RMBFORMAT函数支持在宜搭的以下场景中使用。

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
RMBFORMAT(number, type)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| number | 是 | 需要格式化的数字。 |
| type | 是 | 格式化后的文本格式类。取值：
-   **1**：角整。
-   **0**：元整。

**说明**： 最末位是元或者角必须要加整字，分及以上更小的单位则不需要加。

 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 格式化后大写的人民币文本。 相应的大写文字为：`零、壹、贰、叁、肆、伍、陆、柒、捌、玖、拾、佰、仟、万、亿、元、角、分、厘`。 |

## 使用示例

下图中公式的执行结果为：`壹拾贰万叁仟肆佰伍拾陆元整`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-ff4mghegi9kbsc7m_1702971611833-df3a748f-276e-422a-ab91-96a5bf9b3da4.png]]

## 体验

格式化为人民币格式，[点击体验效果](https://www.aliwork.com/o/wewesd?ddtab=true)。
