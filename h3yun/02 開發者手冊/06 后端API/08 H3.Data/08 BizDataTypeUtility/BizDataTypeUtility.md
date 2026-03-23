---
title: "BizDataTypeUtility"
source: "https://help.h3yun.com/contents/454/674.html"
category: "開發者手冊 / 后端API / H3.Data / BizDataTypeUtility"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizDataTypeUtility
说明 : 逻辑数据类型与数据类型名的转换器 
成员 : 

| 名称 | 说明 |
| --- | --- |
| ShortStringLength | 短文本类型的字符串的最大长度 |
| StringLength | 字符串类型的最大长度 |


方法名称 : IsAttachmentType(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 逻辑类型 |
| 返回值 |  |
| 如果是附件类型，则返回true；否则返回false |  |


方法名称 : IsImage(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 逻辑类型 |
| 返回值 |  |
| 如果是图片类型，则返回true;否则返回false |  |


方法名称 : IsComparable(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 逻辑类型 |
| 返回值 |  |
| 如果可以比较，则返回true；否则返回false |  |


方法名称 : IsNumericType(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 逻辑类型 |
| 返回值 |  |
| 如果是数值型，则返回true；否则返回false |  |


方法名称 : GetBizObjectSupportTypes

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 业务对象支持的类型 |  |


方法名称 : IsBizObjectSupportedType(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 类型 |
| 返回值 |  |
| 如果是业务对象支持的类型，则返回true，否则返回false |  |


方法名称 : ToBizDataTypeName(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 逻辑类型 |
| 返回值 |  |
| 类型名称 |  |


方法名称 : ToRealType(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 逻辑类型 |
| 返回值 |  |
| 运行态的类型 |  |


方法名称 : ToDbType(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 数据逻辑类型 |
| 返回值 |  |
| 数据库字段类型 |  |


方法名称 : ToDbTypeName(H3.Data.Database.DatabaseType,H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "databaseType" | 数据库类型 |
| "type" | 逻辑类型 |
| 返回值 |  |
| 数据库字段类型 |  |


方法名称 : ToBizDataType(System.Type,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "realType" | 实际类型 |
| "length" | 实际类型的长度 |
| 返回值 |  |
| 实际类型对应的逻辑类型 |  |


方法名称 : ToBizDataType(System.Type)

| 参数 | 说明 |
| --- | --- |
| "realType" | 实际类型 |
| 返回值 |  |
| 实际类型对应的逻辑类型 |  |


方法名称 : IsPrimitiveType(System.Type)

| 参数 | 说明 |
| --- | --- |
| "type" | .Net类型 |
| 返回值 |  |
| 如果是非复合类型，则返回true，否则返回false |  |


方法名称 : IsBizStructureSchemaSupported(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 数据类型 |
| 返回值 |  |
| 如果支持该类型则返回true，否则返回false |  |


方法名称 : IsDataTableSupported(System.Type)

| 参数 | 说明 |
| --- | --- |
| "type" | .Net类型 |
| 返回值 |  |
| 如果该类型是数据库表支持的类型，则返回true，否则返回false |  |


方法名称 : IsProcedureSupported(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 数据类型 |
| 返回值 |  |
| 如果存储过程支持该类型则返回true，否则返回false |  |


方法名称 : GetSerializeMethod(H3.Data.BizDataType,H3.Data.Serialization.PropertySerializeMethod@,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "type" | 数据类型 |
| "method" | 序列化方法 |
| "length" | 序列化的长度 |
| 返回值 |  |
| 如果改类型需要序列化，则返回true；否则返回false |  |


方法名称 : CanSort(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 数据逻辑类型 |
| 返回值 |  |
| 如果能支持排序，则返回true，否则返回false |  |


方法名称 : CanSortByChinese(H3.Data.BizDataType)

| 参数 | 说明 |
| --- | --- |
| "type" | 数据逻辑类型 |
| 返回值 |  |
| 如果能支持排序，则返回true，否则返回false |  |