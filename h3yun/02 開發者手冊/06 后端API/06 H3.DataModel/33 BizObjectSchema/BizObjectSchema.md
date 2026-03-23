---
title: "BizObjectSchema"
source: "https://help.h3yun.com/contents/372/390.html"
category: "開發者手冊 / 后端API / H3.DataModel / BizObjectSchema"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizObjectSchema
说明 : 业务对象的模式，在该类中定义了这个类型的业务对象的属性名称、属性类型、方法名称、方法返回值等信息 属性 : 

| 名称 | 说明 |
| --- | --- |
| ObjectTypeId | 业务对象模式在引擎中的类型 |
| SchemaCode | 唯一编码 |
| AccessPointType | 业务服务编码 |
| UsageType | 获取或设置数据模型的应用方式 |
| DisplayName | 显示名称 |
| FullName | 业务对象模式的全名称，该名称由显示名称和编码组合而成，所以，该名称是可以变化的，不能作为唯一确定业务对象模式的键值 |
| Description | 业务对象模式的描述 |
| MainVersion | 主版本号。该版本号由用户控制，用户选择发布一次才会增加1 |
| SubVersion | 次版本号。该版本号由系统控制，每更新一次增加1 |
| VersionNumber | 版本号，该属性由主版本号和此版本号构成 |
| ParentSchema | 如果本模式是其他模式的子模式，那么在这里指定对应的父模式 |
| ParentPropertyName | 如果本模式是其他模式的子模式，那么在这里指定对应的父模式中自己所对应的属性名称 |
| ChildSchemas | 本模式拥有的全部递归子模式，即子模式和子模式的ChildSchemas |
| EnableSeqNo | 是否启用流水号 |
| SeqNoDateFormat | 流水号的日期格式 |
| SeqNoPrefix | 流水号的前置字符串 |
| SeqNoLength | 流水号的总长度 |
| SubmitRules | 表单提交规则 |
| TableName | 映射到本地表的表名称 |
| PropertySchemaCollection | 属性模式集合 |
| Properties | 所有直接的属性 |
| PropertiesExcludeRemoved | 排除已经标注为删除的属性 |
| Views | 业务对象模式对应的视图的集合 |
| NameSchema | 摘要信息，比如：{OwnerId}发表了文章{Title} |
| SummarySchema | 摘要信息，比如：{OwnerId}发表了文章{Title} |
| IconId | 流水号的日期格式 |
| ChangeRules | 业务规则 |
| ChangeEventHandler | 变更事件处理器，变更事件包括添加、删除和修改 |
| EventHandlerConfigured | 是否配置事件处理逻辑 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| MaxCodeLength | 编码的最大长度 |
| CodeRegex | 编码规则:包含字母、数字、下划线 |
| MaxPropertyNameLength | 属性名称的最大长度 |
| PropertyName\_ObjectId | 属性名称：主键的ID |
| PropertyName\_ParentObjectId | 属性名称：父对象 |
| PropertyName\_ModifiedBy | 属性名称：最后的修改人 |
| DefaultDisplayName\_ModifiedTime | 属性显示名称：修改时间 |
| PropertyName\_ModifiedTime | 属性名称：最后的修改时间 |
| PropertyName\_CreatedBy | 属性名称：创建人 |
| DefaultDisplayName\_CreatedBy | 默认显示名称 |
| PropertyName\_OwnerId | 属性名称：所有人ID，这个字段是用来控制权限的，比如：只有Owner才可以对该对象进行读写 |
| DefaultDisplayName\_OwnerId | 默认显示名称 |
| PropertyName\_OwnerDeptId | 属性名称：所有人的父对象ID，这个字段是用来控制权限的，比如：只有Owner所在的部门的成员才可以对该对象进行读写 |
| DefaultDisplayName\_OwnerDeptId | 默认显示名称 |
| PropertyName\_CreatedTime | 属性名称：创建时间 |
| DefaultDisplayName\_CreatedTime | 默认显示名称 |
| PropertyName\_BizObjectType | 属性名称：项目类型 |
| PropertyName\_FolderId | 属性名称：父目录的ID |
| PropertyName\_FileContent | 属性名称：父目录的ID |
| PropertyName\_Name | 属性名称：文件/目录名称 |
| DefaultDisplayName\_Name | 默认显示名称 |
| PropertyName\_WorkflowInstanceId | 属性名称：这个属性用来记录正在运行的流程ID |
| PropertyName\_IconId | 属性名称：图标的Id |
| PropertyName\_Status | 属性名称：生效状态 |
| PropertyName\_SeqNo | 属性名称：流水号 |
| DefaultDisplayName\_SeqNo | 默认显示名称 |
| PropertyName\_Summary | 摘要 |
| PropertyName\_MobileSummary | 移动端用到的一个key |
| PropertyName\_MobileDicData | 移动端用到的一个key |
| PropertyName\_Telephone | 移动端用到的一个key |
| PropertyName\_PrintQrCode | 属性名称：打印二维码 |
| DefaultDisplayName\_PrintQrCode | 默认显示名称 |
| PropertyName\_PrintTime | 属性名称：打印时间 |
| DefaultDisplayName\_PrintTime | 默认显示名称 |
| PropertyName\_Printer | 属性名称：打印人 |
| DefaultDisplayName\_Printer | 默认显示名称 |
| PropertyName\_PrintComment | 属性名称：打印审批意见 |
| DefaultDisplayName\_PrintComment | 默认显示名称 |
| PropertyName\_PrintCompanyName | 属性名称:打印配置 |
| DefaultDisplayName\_PrintCompanyName | 默认显示名称 |
| MethodName\_Create | 新建方法 |
| MethodName\_Load | 加载方法 |
| MethodName\_Remove | 删除方法 |
| MethodName\_Update | 更新方法 |
| MethodName\_GetList | 搜索 |


方法名称 : \_BizObjectSchema(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 业务对象模式编码 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.DataModel.UsageType,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "type" | |
| "schemaCode" | |
| "isRootSchema" | |
| 返回值 |  |
| |  |


方法名称 : GetRootSchema

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetRootSchema(System.String\[\]@)

| 参数 | 说明 |
| --- | --- |
| "properties" | 如何从根模式中找到自己 |
| 返回值 |  |
| 根模式，如果自己就是根模式的话，则返回自己 |  |


方法名称 : GetRecursiveSchemaCodes(System.Boolean)

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetChildSchema(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 子模式的编码 |
| 返回值 |  |
| 子模式 |  |


方法名称 : GetReferenceSchemaCodes

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : EnsureIconIdProperty

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetReservedProperties

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : IsReservedProperty(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| 如果是保留字段则返回true，否则返回false |  |


方法名称 : IsEditable(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| 如果是可写的系统字段，则返回True，如果是不可写的系统字段则返回False，如果不是系统字段则返回Unspecified |  |


方法名称 : IsBoReservedPropertiesOnly(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| 如果只是Bo的保留字则返回true，否则返回false |  |


方法名称 : GetBoReservedPropertiesOnly

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 保留属性 |  |


方法名称 : GetTableName(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 业务对象模式编码 |
| 返回值 |  |
| 表名称 |  |


方法名称 : GetSchemaCodeFromTableName(System.String)

| 参数 | 说明 |
| --- | --- |
| "tableName" | 表名称 |
| 返回值 |  |
| 业务对象模式编码 |  |


方法名称 : GetPrintConfigProperties

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetPrintConfigProperty(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | |
| 返回值 |  |
| |  |


方法名称 : GetPrintProperties

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetProperty(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| 属性模式 |  |


方法名称 : AddProperty(H3.DataModel.PropertySchema)

| 参数 | 说明 |
| --- | --- |
| "property" | 属性模式 |
| 返回值 |  |
| 如果添加成功则返回true，否则返回false |  |


方法名称 : HasRelatedMember

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetPropertyNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 属性名称 |  |


方法名称 : UpdateProperty(System.String,H3.DataModel.PropertySchema)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| "property" | 新的属性模式 |
| 返回值 |  |
| 如果更新成功则返回true；否则返回false |  |


方法名称 : RemoveProperty(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| |  |


方法名称 : GetBizDataType(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 字段名称 |
| 返回值 |  |
| 字段类型 |  |


方法名称 : GetDefaultMethods

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 所有默认方法的名称 |  |


方法名称 : IsDefaultMethod(System.String)

| 参数 | 说明 |
| --- | --- |
| "methodName" | 方法名称 |
| 返回值 |  |
| 如果是默认的方法，则返回true；否则返回false |  |


方法名称 : ValidateFormula(System.String)

| 参数 | 说明 |
| --- | --- |
| "formula" | 表达式 |
| 返回值 |  |
| 如果表达式是合法的，则返回true；否则返回false |  |


方法名称 : ValidateFormula(System.String,System.Boolean,System.Collections.Generic.List{System.String})

| 参数 | 说明 |
| --- | --- |
| "formula" | 表达式 |
| "includeWorkflowKeywords" | 是否包含流程的关键字 |
| "errors" | |
| 返回值 |  |
| 如果表达式是合法的，则返回true；否则返回false |  |


方法名称 : GetNameRelatedProperties

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 与摘要相关的所有属性 |  |


方法名称 : GetSummaryRelatedProperties

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 与摘要相关的所有属性 |  |


方法名称 : GetEffectiveProcedureName

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 生效过程的名称 |  |


方法名称 : GetCancelProcedureName

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 取消过程的名称 |  |


方法名称 : HasEffectRules

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 如果配置了非文件类的事件处理脚本，则返回true |  |


方法名称 : HasCancelRule

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 如果配置了非文件类的事件处理脚本，则返回true |  |


方法名称 : HasEffectFileRules

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 如果配置了非文件类的事件处理脚本，则返回true |  |


方法名称 : HasCancelFileRule

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 如果配置了非文件类的事件处理脚本，则返回true |  |


方法名称 : CreateFromXml(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 业务对象模式编码 |
| "xml" | 业务对象模式的XML定义 |
| 返回值 |  |
| 新建的业务对象模式 |  |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | |
| 返回值 |  |