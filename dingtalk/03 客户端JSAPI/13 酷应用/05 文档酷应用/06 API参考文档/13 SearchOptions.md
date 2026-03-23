---
title: "SearchOptions"
source: "https://open.dingtalk.com/document/development/searchoptions"
category: "客户端JSAPI / 酷应用 / 文档酷应用 / API参考文档"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-searchoptions_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-searchoptions_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

## API描述

搜索选项。用于Sheet.findAll()、Range.find()、Range.findNext()或者Range.findPrevious()等API中指定搜索方式。

## 属性说明

| 属性 | 类型 | 是否必填 | 说明 |
| --- | --- | --- | --- |
| matchEntireCell | boolean | 否 | 匹配整个单元格。 |
| matchCase | boolean | 否 | 匹配大小写。 |
| useRegExp | boolean | 否 | 使用正则表达式。 |
| matchFormulaText | boolean | 否 | 在公式内搜索。 |