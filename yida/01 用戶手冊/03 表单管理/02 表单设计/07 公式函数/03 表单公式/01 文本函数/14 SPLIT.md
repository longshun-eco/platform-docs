---
title: "SPLIT"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/wcguece1v2ok8b00/yf6hkwf5lzcyin93"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 文本函数"
updated: 
tags:
  - yida
  - 用戶手冊
---
**SPLIT**函数用于将文本按照某个标识，分割成多个文本。

## 支持产品场景

SPLIT函数支持在宜搭的以下场景中使用。

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
SPLIT(text, text_separator)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| text | 是 | 被分割的源文本。 |
| text_separator | 是 | 文本标识，如果文本标识为，需要写为`\`。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 分割后的文本列表。 |

## 使用示例

下图中公式的执行结果为：`["宜搭","低代码","应用","开发平台"]`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-yf6hkwf5lzcyin93_1702979505731-e36da346-6fc9-4aea-8af3-35a0e42d3e60.png]]

## 体验

将文本按指定字符串分割成数组，需要配合 **ARRAYGET** 函数使用，[点击体验效果](https://www.aliwork.com/o/wweret?ddtab=true)。
