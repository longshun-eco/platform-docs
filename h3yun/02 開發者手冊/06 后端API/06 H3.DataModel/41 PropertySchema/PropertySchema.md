---
title: "PropertySchema"
source: "https://help.h3yun.com/contents/380/415.html"
category: "開發者手冊 / 后端API / H3.DataModel / PropertySchema"
updated: 2025-12-19
tags:
  - h3yun
  - 開發者手冊
---
类名 : PropertySchema
说明 : 业务对象模式的属性模式 属性 : 

| 名称 | 说明 |
| --- | --- |
| TypeSearchable | 该类型在数据库中是否可以进行搜索 |
| ChildSchema | 关联的业务对象模式的编码 |
| AssociationSchemaCode | 如果该字段是一个关联字段，那么这里记录关联的类型，有两种：固定关联某一个Schema下面的某个对象，如果是固定的，那么这里记录的是SchemaCode，如果是变化的，那么这里记录是哪个字段记录SchemaCode |
| AssociationMappings | 关联字段，本对象与关联对象之间的关联关系，这里记录的（本对象属性，关联对象属性） |
| DataDictItemName | 多选框、下拉框、单选按钮绑定的数据字典名称 |
| OptionalValues | 多选框、下拉框、单选按钮的选项（值1;值2;.....） |
| DisplayFormat | 显示格式 |
| UnitSelectionRange | 选人限制范围，使用";"分割的UnitId |
| ComputationRule | 公式 |
| HideRule | 隐藏规则，替换原来的DisplayRule，对DisplayRule取反 |
| AssociationFilter | 关联查询过滤规则 |
| NoRepeat | 不允许重复，即录入的表单中字段值在历史记录中不存在 |
| ShowMode | 数值控件显示模式，例如是否显示千位分隔符等。后续可扩展各种模式 |
| SelectShowMode | 数值控件显示模式，例如是否显示千位分隔符等。后续可扩展各种模式 |
| IsMappingProperty | 标记控件是否是关联属性控件 |
| TypeIndexable | 是否可以创建索引 |
| Indexed | 是否已经在数据库中创建了索引。索引一旦创建，则禁止取消 |
| Trackable | 是否记录痕迹 |
| IsRelatedMember | 该字段是否是是相关用户字段，如果是，那么记录在该字段上的用户，将拥有该对象的访问权限 |
| Removable | 该字段是否可以从表单上删除，对于系统字段，字段可以从表单上被移除，但是Schema中是不会被移除的，对于自定义字段，用户可以从表单和Schema中移除 |
| IsCustom | 该字段是否是自定义的 |
| MarkAsDeleted | 已删除字段：对预装字段的删除，不能从物理删除 |
| RelatedReportCode | 记录引用这个字段的报表ColumnObjectId(关联字段和排序） |
| QueryItemCode | 记录作为搜索条件的字段 |



构造方法名称 : #ctor(System.String,System.String,System.Boolean,H3.Data.BizDataType,System.Int32,System.Object,System.String,System.String,System.String,System.String,System.String,System.Boolean,System.Boolean,System.String,System.String,System.Boolean,H3.DataModel.PropertyShowMode,H3.DataModel.PropertySelectShowMode,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "PropertyName" | 属性名称，在一个业务对象模式中属性名称不能重复 |
| "DataDictItemName" | 绑定的数据字典名称 |
| "Indexed" | 是否创建索引 |
| "DisplayName" | 显示名称 |
| "DataType" | 属性类型 |
| "MaxLength" | 最大长度 |
| "DefaultValue" | 默认值 |
| "ComputationRule" | 获得值用的计算公式 |
| "Trackable" | 是否记录痕迹 |
| "IsRelatedMemberProperty" | 是否相关成员属性 |
| "OptionalValues" | 自定义值 |
| "DisplayFormat" | 显示 |
| "HideRule" | 隐藏规则 |
| "AssociationFilter" | 关联查询过滤 |
| "UnitSelectionRange" | 组织机构选择范围 |
| "NoRepeat" | 不允许重复 |
| "ShowMode" | 显示模式 |
| "SelectShowMode" | 下拉框显示模式 |
| "isMappingProperty" | 是否是关联属性 |
| 返回值 |  |
| |  |


方法名称 : Update(System.String,System.String,System.Boolean,System.String,H3.Data.BizDataType,System.Int32,System.Object,System.String,System.String,System.String,System.Boolean,System.Boolean,System.Boolean,System.Boolean,System.String,System.String,System.Boolean,System.Collections.Generic.Dictionary{System.String,System.String},System.String,System.Boolean,H3.DataModel.PropertyShowMode,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "ItemName" | 属性名称，在一个业务对象模式中属性名称不能重复 |
| "DataDictItemName" | 绑定的数据字典名称 |
| "Indexed" | 是否创建索引 |
| "DisplayName" | 显示名称 |
| "BizDataType" | 属性类型 |
| "MaxLength" | 最大长度 |
| "DefaultValue" | 默认值 |
| "Formula" | 计算公式 |
| "HideRule" | 隐藏规则 |
| "AssociationFilter" | 关联表单过滤条件 |
| "Trackable" | 是否记录痕迹 |
| "IsRelatedMemberProperty" | 是否相关人员属性 |
| "IsCustom" | 是否自定义 |
| "Removable" | 可移除 |
| "OptionalValues" | 选项值 |
| "DisplayFormat" | 显示格式 |
| "MarkAsDeleted" | 标记为删除 |
| "AssociationMappings" | 关联表单映射 |
| "UnitSelectionRange" | 选人范围 |
| "NoRepeat" | 不能重复 |
| "ShowMode" | 显示模式 |
| "AssociationSchemaCode" | 下拉框关联表单 |
| "isMappingProperty" | 是否关联属性 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.String,H3.Data.BizDataType,H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "ItemName" | 属性名称，在一个业务对象模式中属性名称不能重复 |
| "DisplayName" | 显示名称 |
| "BizDataType" | 属性类型 |
| "ChildBOSchema" | 属性的子业务对象模式 |
| 返回值 |  |
| |  |


方法名称 : Update(System.String,System.String,H3.Data.BizDataType,H3.DataModel.BizObjectSchema,System.String,System.String,System.Boolean,System.String,System.Boolean,H3.DataModel.PropertyShowMode)

| 参数 | 说明 |
| --- | --- |
| "ItemName" | 属性名称，在一个业务对象模式中属性名称不能重复 |
| "DisplayName" | 显示名称 |
| "BizDataType" | 属性类型 |
| "ChildSchema" | 属性的子业务对象模式 |
| "HideRule" | 隐藏规则 |
| "AssociationFilter" | 关联表单过滤条件 |
| "MarkAsDeleted" | 标记为已删除 |
| "UnitSelectionRange" | 选人范围 |
| "NoRepeat" | 不能重复 |
| "ShowMode" | 显示模式 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(System.String,System.Boolean,System.String,H3.Data.BizDataType,System.Boolean,System.Boolean,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称，在一个业务对象模式中属性名称不能重复 |
| "Indexed" | 是否创建索引 |
| "DisplayName" | 显示名称 |
| "BizDataType" | 属性类型 |
| "Trackable" | 是否记录痕迹 |
| "IsRelatedMemberProperty" | 是否相关人员属性 |
| "AssociationSchemaCode" | 关联表单 |
| "isMappingProperty" | 是否关联属性 |
| 返回值 |  |
| |  |


方法名称 : Update(System.String,System.Boolean,System.String,H3.Data.BizDataType,System.String,System.String,System.Boolean,System.Boolean,System.String,System.Collections.Generic.Dictionary{System.String,System.String},System.Boolean,System.String,System.Boolean,H3.DataModel.PropertyShowMode,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : OnMethodRemoved(System.String)

| 参数 | 说明 |
| --- | --- |
| "MethodName" | 方法名称 |
| 返回值 |  |
| |  |


方法名称 : GetSerializeMethod

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : OnFieldNameChanged(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "OldFieldName" | 旧的字段名称 |
| "NewFieldName" | 新的字段名称 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetFormatedDateTime(System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "dt" | DateTime值 |
| 返回值 |  |
| |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | |
| 返回值 |  |
| |  |