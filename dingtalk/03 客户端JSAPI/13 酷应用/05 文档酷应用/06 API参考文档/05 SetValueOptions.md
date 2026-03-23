---
title: "SetValueOptions"
source: "https://open.dingtalk.com/document/development/setvalueoptions"
category: "客户端JSAPI / 酷应用 / 文档酷应用 / API参考文档"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-setvalueoptions_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-setvalueoptions_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

## API描述

设置值的选项。用于 Range.setValue()或者Range.setValues() API中指定设置值时的选项。

## 属性说明

| 属性 | 类型 | 是否必填 | 说明 |
| --- | --- | --- | --- |
| parseType | String | 是 | 值的解析类型。   * **raw**：表示设置值的时候不解析。 * **useEntered**：表示策略和用户输入一致，例如输入 100%，会被解析成值为1，数字格式为%。 |