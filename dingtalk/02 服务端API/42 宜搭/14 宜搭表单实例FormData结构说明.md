---
title: "宜搭表单实例FormData结构说明"
source: "https://open.dingtalk.com/document/development/formdata-structure-description-for-returned-form-instances"
category: "服务端API / 宜搭"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-formdata-structure-description-for-returned-form-instances_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-formdata-structure-description-for-returned-form-instances_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23本文介绍了宜搭表单实例FormData格式。

## FormData示例

```
     {
      //单行文本
      "textField_l28nuccb":"单行文本",
      //多行文本
      "textareaField_l28nuccc":"多行文本",
      //数值
      "numberField_l28nuccd":100,
      "numberField_l28nuccd_value":"100",
      //单选
      "selectField_l28nucch_id":"选项一",
      "selectField_l28nucch":"选项一",
      //复选
      "multiSelectField_l28nucci":["选项一","选项二"],
      "multiSelectField_l28nucci_id":["选项一","选项二"],
      //评分
      "rateField_l28nuccg":5,
      "rateField_l28nuccg_value":"5",
      //下拉单选
      "radioField_l28nucce":"选项一",
      "radioField_l28nucce_id":"选项一",
      //下拉复选
```