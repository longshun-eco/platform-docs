---
title: "ReportSourceAssociation"
source: "https://help.h3yun.com/contents/554/502.html"
category: "開發者手冊 / 后端API / H3.Reporting / ReportSourceAssociation"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : ReportSourceAssociation
说明 : 数据源关联 属性 : 

| 名称 | 说明 |
| --- | --- |
| RootSchemaCode | 根数据模型编码 |
| SchemaCode | 数据模型编码 |
| MasterField | 主表字段编码,tableName.replace('-','')+'\_'+fieldname |
| SubField | 关联表字段编码,tableName.replace('-','')+'\_'+fieldname |
| Mode | 关联表字段编码 |
| Method | 关联关系构建方式 |
| IsSubSheet | 是否子表字段 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_RootSchemaCode | 数据模型编码属性名称 |
| \_RootSchemaCode | 数据模型编码 |
| PropertyName\_SchemaCode | 数据模型编码属性名称 |
| \_SchemaCode | 数据模型编码 |
| PropertyName\_MasterField | 主表字段编码属性名称 |
| \_MasterField | 主表字段编码 |
| PropertyName\_SubField | 关联表字段编码属性名称 |
| \_SubField | 关联表字段编码 |
| PropertyName\_Mode | 关联模式编码属性名称 |
| \_Mode | 关联表字段编码 |
| PropertyName\_Method | 关联关系构建方式 方便前端展示时判断是否需要编辑 |
| \_Method | 关联关系构建方式 |
| PropertyName\_IsSubSheet | 是否排序字段 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |