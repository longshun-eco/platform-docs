---
title: "feature字段"
source: "https://open.dingtalk.com/document/development/feature-field"
category: "服务端API / 行业开放 / 新教育 / 家校通讯录2.0"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-feature-field_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-feature-field_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23

| **名称** | 类型 | 示例 | 备注 |
| --- | --- | --- | --- |
| period\_type | String | kindergarten | **此字段只有经典模型的period部门类型下才有效。**  学段类型：   * **kindergarten**：幼儿园 * **primary\_school**：小学 * **middle\_school**：初中 * **high\_school**：高中 |
| name\_mode | String | number | **此字段只有在经典模型的period部门类型下才有效。**  学段名称类型：   * **text**：文本型，如中学为七年级，八年级，九年级 * **number**：数字型，如初中一年级1班，二年级1班等 |
| grade\_level | Number | 1 | **此字段只有经典模型的class和grade部门类型下才有效。**  年级级数，一年级为1，二年级为2。 |
| start\_year | String | 2020 | **此字段只有经典模型的****grade****部门类型下才有效。**  入学年份。 |
| class\_level | Number | 1 | **此字段只有经典模型的****class****部门类型下才有效。**  每个年级下班级级数，1班为1，2班为2。 |