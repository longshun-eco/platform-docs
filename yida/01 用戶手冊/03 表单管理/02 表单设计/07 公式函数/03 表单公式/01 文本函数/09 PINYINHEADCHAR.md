---
title: "PINYINHEADCHAR"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/wcguece1v2ok8b00/dvfmdhg8i3ohg0c4"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 文本函数"
updated: 
tags:
  - yida
  - 用戶手冊
---

**PINYINHEADCHAR** 函数可以将字符串中的每个字的首字母以大写形式拼接返回。

**说明**：

暂不支持获取英文句子的首字母，如果是字母，会将其转换为大写字母返回。

## 支持产品场景

PINYINHEADCHAR 函数支持在宜搭的以下场景中使用。

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
PINYINHEADCHAR(text)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| text | 是 | 需要获取大写首字母的文本内容。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 文本的大写首字母。 |

## 使用示例

下图中公式的执行结果为：`YDDDM`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-dvfmdhg8i3ohg0c4_1702891249855-b9dff1ca-803b-47ff-a7c8-3531069b56c1.png]]

## 体验

返回中文的大写首字母，小写英文的大写字母，[**点击体验效果**](https://www.aliwork.com/o/wedacsdxax?ddtab=true)
