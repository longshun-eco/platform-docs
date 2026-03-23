---
title: "Variant"
source: "https://help.h3yun.com/contents/441/626.html"
category: "開發者手冊 / 后端API / H3.DataModel.Script / Variant"
updated: 2025-12-17
tags:
  - h3yun
  - 開發者手冊
---
类名 : Variant
说明 : 变量 属性 : 

| 名称 | 说明 |
| --- | --- |
| Value | 值 |
| IsNullOrEmpty | 是否为空 |
| Type | 逻辑类型 |
| IsArray | 因为数据类型中，并不支持数组类型，所以在这里特地标记下这个是数组 |
| Name | 名称 |



构造方法名称 : #ctor(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "Type" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Object)

| 参数 | 说明 |
| --- | --- |
| "o" | Object对象 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Object,System.String,H3.Data.BizDataType,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "o" | 对象 |
| "name" | 名称 |
| "type" | 类型 |
| "isArray" | 是否数组 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Object,H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "o" | |
| "Type" | |
| 返回值 |  |
| |  |


方法名称 : \_Variant(System.Object)

| 参数 | 说明 |
| --- | --- |
| "o" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "v" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "b" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Int32)

| 参数 | 说明 |
| --- | --- |
| "i" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.Double)

| 参数 | 说明 |
| --- | --- |
| "d" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String)

| 参数 | 说明 |
| --- | --- |
| "s" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "dt" | |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.TimeSpan)

| 参数 | 说明 |
| --- | --- |
| "ts" | |
| 返回值 |  |
| |  |


方法名称 : ToString

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetHashCode

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Equals(System.Object)

| 参数 | 说明 |
| --- | --- |
| "o" | |
| 返回值 |  |
| |  |


方法名称 : op\_Implicit(H3.DataModel.Script.Variant)~System.Boolean

| 参数 | 说明 |
| --- | --- |
| "v" | |
| 返回值 |  |
| |  |


方法名称 : op\_Implicit(H3.DataModel.Script.Variant)~System.Int32

| 参数 | 说明 |
| --- | --- |
| "v" | |
| 返回值 |  |
| |  |


方法名称 : op\_Implicit(H3.DataModel.Script.Variant)~System.Double

| 参数 | 说明 |
| --- | --- |
| "v" | |
| 返回值 |  |
| |  |


方法名称 : op\_Implicit(H3.DataModel.Script.Variant)~System.DateTime

| 参数 | 说明 |
| --- | --- |
| "v" | |
| 返回值 |  |
| |  |


方法名称 : op\_Implicit(H3.DataModel.Script.Variant)~System.TimeSpan

| 参数 | 说明 |
| --- | --- |
| "v" | |
| 返回值 |  |
| |  |


方法名称 : op\_Implicit(H3.DataModel.Script.Variant)~System.String

| 参数 | 说明 |
| --- | --- |
| "v" | |
| 返回值 |  |
| |  |


方法名称 : op\_Implicit(System.String)~H3.DataModel.Script.Variant

| 参数 | 说明 |
| --- | --- |
| "s" | |
| 返回值 |  |
| |  |


方法名称 : op\_UnaryNegation(H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "a" | |
| 返回值 |  |
| |  |


方法名称 : op\_LogicalNot(H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "a" | |
| 返回值 |  |
| |  |


方法名称 : op\_UnaryPlus(H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "a" | |
| 返回值 |  |
| |  |


方法名称 : op\_Addition(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | |
| "a" | |
| 返回值 |  |
| |  |


方法名称 : op\_Subtraction(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | |
| "a" | |
| 返回值 |  |
| |  |


方法名称 : op\_Multiply(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | |
| "a" | |
| 返回值 |  |
| |  |


方法名称 : op\_Division(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | |
| "a" | |
| 返回值 |  |
| |  |


方法名称 : op\_BitwiseAnd(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | |
| "a" | |
| 返回值 |  |
| |  |


方法名称 : op\_BitwiseOr(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | |
| "a" | |
| 返回值 |  |
| |  |


方法名称 : op\_GreaterThan(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | 变量a |
| "a" | 变量b |
| 返回值 |  |
| |  |


方法名称 : op\_LessThan(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | 变量b |
| "a" | 变量a |
| 返回值 |  |
| |  |


方法名称 : op\_GreaterThanOrEqual(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | 变量b |
| "a" | 变量a |
| 返回值 |  |
| |  |


方法名称 : op\_LessThanOrEqual(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | 变量b |
| "a" | 变量a |
| 返回值 |  |
| |  |


方法名称 : op\_Equality(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | 变量b |
| "a" | 变量a |
| 返回值 |  |
| |  |


方法名称 : op\_Inequality(H3.DataModel.Script.Variant,H3.DataModel.Script.Variant)

| 参数 | 说明 |
| --- | --- |
| "b" | 变量b |
| "a" | 变量a |
| 返回值 |  |