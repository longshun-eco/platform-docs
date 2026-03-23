---
title: "PropertyEventHandler"
source: "https://help.h3yun.com/contents/364/379.html"
category: "開發者手冊 / 后端API / H3.DataModel / PropertyEventHandler"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : PropertyEventHandler
说明 : 变更事件的处理逻辑之一：变更对象属性。变更属性的逻辑是，首先根据IdPropertyName获得TargetObject，然后TargetObject\[UpdatePropertyName\] = SelfObject\[ValuePropertyName\]或者TargetObject\[UpdatePropertyName\] +/-= SelfObject\[ValuePropertyName\] 属性 : 

| 名称 | 说明 |
| --- | --- |
| IdPropertyName | 获得要变更的对象的SchemaCode和ObjectID的属性，这个SchemaCode和ObjectId是存储在SelfObject的属性中，该字段指定了这个属性的属性名称 |
| SourcePropertyName | 这个属性指定了SelfObject的某个值要变更到TargetObject上 |
| FixedValue | 这个属性指定了一个固定值变更到TargetObject上 |
| SourcePropertyNameOnCancel | 在取消时,且计算规则为赋值，将该属性的值变更到TargetObject上 |
| FixedValueOnCancel | 在取消时,且计算规则为赋值，将该固定值变更到TargetObject上 |
| DestPropertyName | 要更新的目标对象的属性 |
| TotalPropertyName | 如果是Subtract模式，那么这里记录TargetObject的汇总值字段。TargetObject\[UpdatePropertyName\] = TargetObject\[TotalPropertyName\] - SelfObject\[ValuePropertyName\] |
| Method | 属性变更方法（添加，更新，移除） |