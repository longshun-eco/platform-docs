---
title: "Hyperlink"
source: "https://open.dingtalk.com/document/development/hyperlink"
category: "客户端JSAPI / 酷应用 / 文档酷应用 / API参考文档"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-hyperlink_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-hyperlink_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

## API描述

超链接。用于Range.getHyperlink()或者Range.setHyperlink() API中访问超链接。

## 属性说明

| 属性 | 类型 | 是否必填 | 说明 |
| --- | --- | --- | --- |
| type | string | 是 | 超链接的类型，可选择以下值。   * **path**：网页链接 * **sheet**：表格引用 * **range**：单元格引用 |
| link | string | 是 | 链接的内容。   * 当type为path，是一个普通网页链接。 * 当type为sheet，是一个SheetName，例如sheet1。 * 当type为range，是一个引用，例如Sheet1!A1。 |
| text | string | 否 | 单元格显示的内容，任意文本。 |