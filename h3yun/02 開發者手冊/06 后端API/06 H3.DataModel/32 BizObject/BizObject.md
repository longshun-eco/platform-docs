---
title: "BizObject"
source: "https://help.h3yun.com/contents/371/386.html"
category: "開發者手冊 / 后端API / H3.DataModel / BizObject"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizObject
说明 : 业务对象。业务对象默认提供对象的创建、获取、更新和删除方法；业务对象不支持序列化，但是其中ValueTable属性是可以序列化 属性 :

| 名称 | 说明 |
| --- | --- |
| PropertyFiles | 用于在提交校验时候存放附件字段的附件信息 |
| AssociatedBizObjectHeaders | 相关联的业务对象的摘要信息，格式是(BizObjectId, BizObjectHeader) |
| UnitNameTable | 与该对象相关的组织信息，格式是(UnitId, UnitName) |
| IsDirty | 业务对象是否包含脏数据 |
| ObjectId | 获取或设置业务对象ID |
| ParentObjectId | 获取或设置业务对象ID |
| Parent | 该对象的主表对象 |
| Name | 业务对象的名称 |
| ModifiedBy | 最后一次修改的人 |
| ModifiedTime | 最后一次修改的时间 |
| CreatedBy | 创建人 |
| CreatedTime | 创建时间 |
| WorkflowInstanceId | 正在运行的流程实例的ID |
| OwnerId | 所有人 |
| OwnerDeptId | 拥有部门的部门ID |
| FolderId | 目录ID |
| IconId | 图标的ID |
| Status | 业务对象的状态，生效、草稿和作废 |
| BizObjectType | 该业务对象的类型 |
| Schema | 业务对象模式，通过该属性可以获得业务对象的属性类型、方法定义等信息 |
| Item(System.String) | 读写属性值，该方法仅适用于业务对象本身的属性，不适用于业务对象关联的对象属性 |
| State | 当前状态，比如：已经加载、加载了但是没有加载出对象等 |
| CurrentViewName | 当前视图的名称 |
| CurrentView | 当前视图，其中，视图定义在业务对象模式中 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| FileTable | (BizObjectID + propertyName, fileList) |
| PropertyName\_Summary | Summary字段的属性名称 |


构造方法名称 : #ctor(H3.IEngine,H3.DataModel.BizObjectSchema,System.String)

| 参数 | 说明 |
| --- | --- |
| "engine" | 引擎 |
| "schema" | 数据模型 |
| "userId" | 操作用户 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.IEngine,H3.DataModel.BizObjectSchema,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "engine" | 引擎 |
| "schema" | 数据模型 |
| "userId" | 操作用户 |
| "userParentId" | 用户的父组织，可以为空，如果为空的话，业务对象在需要的时候会自动加载，请尽量传入该参数，以减少系统开销 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Organization.IOrganization,H3.Data.IDataDictManager,H3.DataModel.IBizObjectManager,H3.DataModel.BizObjectSchema,System.String)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "dataDictManager" | 数据字典管理器 |
| "bizObjectManager" | 业务对象管理器 |
| "schema" | 业务对象模式 |
| "userId" | 用户Id |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Organization.IOrganization,H3.Data.IDataDictManager,H3.DataModel.IBizObjectManager,H3.DataModel.BizObjectSchema,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "dataDictManager" | 数据字典管理器 |
| "bizObjectManager" | 业务对象管理器 |
| "schema" | 业务对象模式 |
| "userId" | 用户Id |
| "userParentId" | 用户的父组织，可以为空，如果为空的话，业务对象在需要的时候会自动加载，请尽量传入该参数，以减少系统开销 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Organization.IOrganization,H3.Data.IDataDictManager,H3.DataModel.IBizObjectManager,H3.DataModel.BizObjectSchema,System.String,System.String,System.String,H3.Data.Serialization.VirtualObject,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{H3.DataModel.BizObjectFileHeader}},System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader},System.Collections.Generic.Dictionary{System.String,System.String})

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "dataDictManager" | 数据字典管理器 |
| "bizObjectManager" | 业务对象管理器 |
| "schema" | 业务对象模式 |
| "userId" | 用户Id |
| "userParentId" | 用户的父组织，可以为空，如果为空的话，业务对象在需要的时候会自动加载，请尽量传入该参数，以减少系统开销 |
| "bizObjectId" | 业务对象Id |
| "virtualObject" | 业务对象的数据集 |
| "fileHeaders" | 业务对象关联的文件 |
| "associatedBoHeaders" | 业务对象关联的业务对象 |
| "unitNameTable" | 业务对象关联的组织 |
| 返回值 |  |
| |  |


方法名称 : GetRoot

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetStatus(H3.Data.Serialization.VirtualObject)

| 参数 | 说明 |
| --- | --- |
| "obj" | 业务对象 |
| 返回值 |  |
| 业务对象的状态 |  |


方法名称 : GetBizObjectType(H3.DataModel.BizObjectSchema,H3.Data.Serialization.VirtualObject)

| 参数 | 说明 |
| --- | --- |
| "schema" | 数据模型 |
| "obj" | 数据 |
| 返回值 |  |
| |  |


方法名称 : GetFile(System.String)

| 参数 | 说明 |
| --- | --- |
| "fileId" | 附件ID |
| 返回值 |  |
| 附件的内容 |  |


方法名称 : GetFileHeaders(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| 文件头列表 |  |


方法名称 : AddFile(H3.DataModel.BizObjectFile)

| 参数 | 说明 |
| --- | --- |
| "file" | 要添加的业务对象的属性上的文件 |
| 返回值 |  |
| 如果添加成功，则返回一个文件的ID，否则返回空 |  |


方法名称 : GetValueTable

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : CreateChildBizObject(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 子对象对隶属于本对象的属性名称 |
| "addToProperty" | 创建后，是否自动赋值给本对象。如果赋值，那么设置新建对象的Parent值，并且：如果本属性是BizObject类型，那么将新建的对象赋值给本属性；如果本属性是BizObject\[\]类型，那么把新建的对象添加到数组的最后面 |
| 返回值 |  |
| 新建的子对象 |  |


方法名称 : Submit

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : ValidateSubmit(System.Boolean,System.String@)

| 参数 | 说明 |
| --- | --- |
| "validateSubmitRule" | 是否需要校验提交规则 |
| "errorMessage" | 提示信息 |
| 返回值 |  |
| |  |


方法名称 : Create(System.Boolean,System.String@)

| 参数 | 说明 |
| --- | --- |
| "validateSubmitRule" | 是否有表单提交规则 |
| "errorMessage" | 提交规则不通过信息 |
| 返回值 |  |
| 如果创建成功则返回Success，否则返回错误代码 |  |


方法名称 : Create

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Create(System.String@)

| 参数 | 说明 |
| --- | --- |
| "errorMessage" | |
| 返回值 |  |
| |  |


方法名称 : Create(H3.DataModel.BulkCommit)

| 参数 | 说明 |
| --- | --- |
| "bulkCommit" | 业务对象提交执行类 |
| 返回值 |  |
| |  |


方法名称 : Load(System.String,H3.IEngine,System.String,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "engine" | 业务对象访问引擎的连接 |
| "schemaCode" | 业务对象模式编码 |
| "objectId" | 业务对象Id |
| "requireRelatedObjects" | |
| "userId" | 用户Id |
| 返回值 |  |
| 加载好的业务对象 |  |


方法名称 : Load

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Load(System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "requireRelatedObjects" | 是否加载相关数据 |
| 返回值 |  |
| |  |


方法名称 : Update(System.Boolean,System.String@)

| 参数 | 说明 |
| --- | --- |
| "validateSubmitRule" | 是否验证表单提交规则 |
| "errorMessage" | 提交规则不通过信息 |
| 返回值 |  |
| 如果创建成功则返回Success，否则返回错误代码 |  |


方法名称 : Update

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Update(System.String@)

| 参数 | 说明 |
| --- | --- |
| "errorMessage" | |
| 返回值 |  |
| |  |


方法名称 : Update(H3.DataModel.BulkCommit)

| 参数 | 说明 |
| --- | --- |
| "bulkCommit" | |
| 返回值 |  |
| |  |


方法名称 : Remove

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 如果删除成功，则返回Success，否则返回错误代码 |  |


方法名称 : Remove(System.Boolean,System.Boolean,H3.DataModel.BizObjectHeader@)

| 参数 | 说明 |
| --- | --- |
| "checkWorkflowInstance" | 是否检查流程实例 |
| "checkReference" | 是否检查引用 |
| "referredObjectHeader" | 引用的业务对象的摘要信息 |
| 返回值 |  |
| 如果删除成功，则返回Success，否则返回错误代码 |  |


方法名称 : Remove(H3.DataModel.BulkCommit)

| 参数 | 说明 |
| --- | --- |
| "bulkCommit" | 业务对象批量执行 |
| 返回值 |  |
| |  |


方法名称 : CalcExpression(System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "expression" | 表达式 |
| "errorMessage" | 错误信息 |
| 返回值 |  |
| 返回值可以是int或者bool或者string等类型的对象 |  |


方法名称 : CalcExpression(System.String)

| 参数 | 说明 |
| --- | --- |
| "expression" | 表达式 |
| 返回值 |  |
| 返回值可以是int或者bool或者string等类型的对象 |  |


方法名称 : CalcExpression\`\`1(System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "expression" | 表达式 |
| "errorMessage" | 异常信息 |
| 返回值 |  |
| 返回值可以是int或者bool或者string等类型的对象 |  |


方法名称 : CalcExpression\`\`1(System.String)

| 参数 | 说明 |
| --- | --- |
| "expression" | 表达式 |
| 返回值 |  |
| 返回值可以是int或者bool或者string等类型的对象 |  |


方法名称 : TryCalcExpression\`\`1(System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "expression" | 表达式 |
| "errorMsg" | 错误信息 |
| 返回值 |  |
| 返回值可以是int或者bool或者string等类型的对象 |  |


方法名称 : TryCalcExpression\`\`1(System.String)

| 参数 | 说明 |
| --- | --- |
| "expression" | 表达式 |
| 返回值 |  |
| 返回值可以是int或者bool或者string等类型的对象 |  |


方法名称 : GetPropertyVisible(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| 该属性在当前视图中是否可见 |  |


方法名称 : GetPropertyEditable(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| 该属性在当前视图中是否可编辑 |  |


方法名称 : GetPropertyRequired(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| 该属性在当前视图中是否必填 |  |


方法名称 : GetPropertyPrintable(System.String)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 属性名称 |
| 返回值 |  |
| 该属性在当前视图中是否可打印 |  |


方法名称 : GetSummary(H3.DataModel.SplitType)

| 参数 | 说明 |
| --- | --- |
| "splitType" | 分隔符 |
| 返回值 |  |
| 解析后的字符串 |  |


方法名称 : GetSummary(System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.Dictionary{System.String,System.String}}@,System.String@,System.String@,System.String@,H3.DataModel.SplitType)

| 参数 | 说明 |
| --- | --- |
| "mobileDicData" | |
| "mobileSummary" | |
| "pcSummary" | |
| "telephone" | |
| "splitType" | |
| 返回值 |  |
| |  |


方法名称 : ParseText(System.String,System.Boolean,H3.DataModel.SplitType)

| 参数 | 说明 |
| --- | --- |
| "text" | 原文本 |
| "includePropertyName" | 解析之后的字符串是否包含属性名称 |
| "splitType" | 分隔符 |
| 返回值 |  |
| 解析后的字符串 |  |


方法名称 : ParseText(System.String,System.Boolean,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.Dictionary{System.String,System.String}}@,System.String@,System.String@,System.String@,H3.DataModel.SplitType)

| 参数 | 说明 |
| --- | --- |
| "text" | 原文本 |
| "includePropertyName" | 解析之后的字符串是否包含属性名称 |
| "mobileDicData" | 移动端键值对summary |
| "mobileSummary" | 解析之后的字符串是否包含属性名称 |
| "pcSummary" | 分隔符 |
| "telephone" | 移动端摘要 |
| "splitType" | 移动端摘要 |
| 返回值 |  |
| 解析后的字符串 |  |


方法名称 : ParseTextStructure(System.String)

| 参数 | 说明 |
| --- | --- |
| "sourceData" | 原文本 |
| 返回值 |  |
| 转换后的数组 |  |


方法名称 : GetMembers

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 业务对象相关的成员 |  |


方法名称 : GetMembers(H3.DataModel.BizObjectSchema,H3.Data.Serialization.VirtualObject)

| 参数 | 说明 |
| --- | --- |
| "schema" | 业务对象模式 |
| "obj" | 业务对象 |
| 返回值 |  |
| 业务对象相关的成员 |  |


方法名称 : GetList(H3.IEngine,System.String,H3.DataModel.BizObjectSchema,H3.DataModel.GetListScopeType,H3.Data.Filter.Filter)

| 参数 | 说明 |
| --- | --- |
| "engine" | 引擎对象 |
| "schema" | 业务对象模式 |
| "userId" | 用户Id |
| "getListScopeType" | 权限范围 |
| "filter" | 过滤条件 |
| 返回值 |  |
| 符合条件的业务对象数组，不过这里的业务对象未必包含全部字段，可能只包括只要求返回的字段 |  |


方法名称 : GetList(H3.IEngine,System.String,H3.DataModel.BizObjectSchema,H3.DataModel.GetListScopeType,System.Boolean,H3.Data.Filter.Filter,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "engine" | 引擎对象 |
| "schema" | 业务对象模式 |
| "userId" | 用户Id |
| "getListScopeType" | 权限范围 |
| "requireAssociatedBoHeaders" | |
| "filter" | 过滤条件 |
| "count" | 如果要求返回总数，则返回符合该过滤条件的总数 |
| 返回值 |  |
| 符合条件的业务对象数组，不过这里的业务对象未必包含全部字段，可能只包括只要求返回的字段 |  |


方法名称 : GetList(H3.Organization.IOrganization,H3.Data.IDataDictManager,H3.DataModel.IBizObjectManager,System.String,H3.DataModel.BizObjectSchema,H3.DataModel.GetListScopeType,System.Boolean,H3.Data.Filter.Filter,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "organization" | 组织机构管理器 |
| "dataDictManager" | 数据字典管理器 |
| "bizObjectManager" | 业务对象管理器 |
| "schema" | 业务对象模式 |
| "userId" | 用户Id |
| "getListScopeType" | 权限范围 |
| "requireRelatedObjects" | 是否加载出相关的数据 |
| "filter" | 过滤条件 |
| "count" | 如果要求返回总数，则返回符合该过滤条件的总数 |
| 返回值 |  |
| 符合条件的业务对象数组，不过这里的业务对象未必包含全部字段，可能只包括只要求返回的字段 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | |
| 返回值 |  |