---
title: "CONCATENATE"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/wcguece1v2ok8b00/mbe6045dlu6ebg33"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 文本函数"
updated: 
tags:
  - yida
  - 用戶手冊
---
**CONCATENATE** 拼接函数用于将多个字符串拼接合并成为一个字符串。

## 支持产品场景

**CONCATENATE** 拼接函数支持在宜搭的以下场景中使用。

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
CONCATENATE(text1,text2,text3....)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| text1,text2,text3.... | 是 | 需要拼接的字符串，多个字符串之间使用英文逗号隔开。
**说明**： 如果值为字符串，需要用引号将字符串包裹起来。

 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 文本 | 拼接完成的字符串。 新字符串的排列顺序为 **CONCATENATE** 函数中属性值的顺序。 例如，输入的公式为 `CONCATENATE("a","b","c")`，那么拼接后输出的新字符串为 `abc`。 |

## 使用示例

下图中公式的执行结果为：`宜搭低代码开发平台`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-wcguece1v2ok8b00-mbe6045dlu6ebg33_1702957762222-296d71d9-9ced-40d3-89d1-ca7b0720d195.png]]

## 体验

将「单行输入框」组件 1、2、3 的值拼接起来，[**点击体验效果**](https://www.aliwork.com/o/qwewedc?ddtab=true)。
