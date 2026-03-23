---
title: "SortField"
source: "https://open.dingtalk.com/document/development/sortfield"
category: "客户端JSAPI / 酷应用 / 文档酷应用 / API参考文档"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-sortfield_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-sortfield_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

## API描述

排序字段。用于Filter.sort() API中指定排序方式。

## 属性说明

| 属性 | 类型 | 是否必填 | 说明 |
| --- | --- | --- | --- |
| column | number | 是 | 表示与range第一列的偏移量。 |
| ascending | boolean | 否 | 指定是否以升序完成排序。   * false：降序，默认值。 * true：升序。 |