---
title: "PropertySchemaSummary"
source: "https://help.h3yun.com/contents/354/361.html"
category: "開發者手冊 / 后端API / H3.DataModel / PropertySchemaSummary"
updated: 2025-12-19
tags:
  - h3yun
  - 開發者手冊
---
类名 : PropertySchemaSummary
说明 : 业务对象的属性的摘要，为了减少网络传输量和提升响应速度，我们尽可能使用该类型 属性 : 

| 名称 | 说明 |
| --- | --- |
| Name | 项目名称 |
| DisplayName | 显示名称 |
| FullName | 项目全名称 |
| MarkAsDeleted | 已删除字段：对预装字段的删除，不能从物理删除 |
| DataType | 数据类型 |
| ChildSchema | 关联的业务对象模式的编码 |
| AssociationSchemaCode | 如果该字段是一个关联字段，那么这里记录关联的类型，有两种：固定关联某一个Schema下面的某个对象，如果是固定的，那么这里记录的是SchemaCode，如果是变化的，那么这里记录是哪个字段记录SchemaCode |
| AssociationFilter | 关联查询过滤规则 |
| DataDictItemName | 多选框、下拉框、单选按钮绑定的数据字典名称 |
| OptionalValues | 多选框、下拉框、单选按钮的选项（值1;值2;.....） |
| DisplayFormat | 显示格式 |
| UnitSelectionRange | 选人限制范围，使用";"分割的UnitId |
| NoRepeat | 不允许重复 |
| ShowMode | 显示模式 |
| IsMappingProperty | 标记是否是关联属性控件 |
| AssociationField | 下拉框关联表单联动时对应关联表单字段 |
| ComputationRule | 计算公式 |



构造方法名称 : #ctor(H3.DataModel.PropertySchema,H3.DataModel.BizObjectSchemaSummary)

| 参数 | 说明 |
| --- | --- |
| "property" | 属性 |
| "parent" | 业务对象模型摘要 |
| 返回值 |  |
| |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | |
| 返回值 |  |
| |
 |