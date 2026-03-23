---
title: "IBizObjectManager"
source: "https://help.h3yun.com/contents/377/407.html"
category: "開發者手冊 / 后端API / H3.DataModel / IBizObjectManager"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : IBizObjectManager
说明 : 数据模型管理器 
方法名称 : AddDraftSchema(H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "schema" | 业务对象模式 |
| 返回值 |  |
| 如果添加成功则返回true；否则返回false |  |


方法名称 : GetDraftSchema(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 业务对象 |
| 返回值 |  |
| 业务对象 |  |


方法名称 : UpdateDraftSchema(H3.DataModel.BizObjectSchema)

| 参数 | 说明 |
| --- | --- |
| "schema" | 业务对象模式 |
| 返回值 |  |
| 如果更新成功，则返回true；否则返回false |  |


方法名称 : GetPublishedSchemaSummaries(System.Boolean,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "getAll" | 是否返回全部业务对象模式，如果是，则不需要指定schemaCodes |
| "schemaCodes" | 如果不是活的所有业务对象模式的摘要，那么在这里指定要返回的业务对象模式的编码 |
| 返回值 |  |
| 业务对象模式列表 |  |


方法名称 : ExistsSchema(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| 返回值 |  |
| |  |


方法名称 : ExistsSchemas(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "schemaCodes" | |
| 返回值 |  |
| |  |


方法名称 : GetPublishedSchemas(System.Boolean,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "getAll" | |
| "schemaCodes" | |
| 返回值 |  |
| |  |


方法名称 : LoadBizObject(System.String,System.String,System.String,System.Boolean,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{H3.DataModel.BizObjectFileHeader}}@,System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader}@,System.Collections.Generic.Dictionary{System.String,System.String}@)

| 参数 | 说明 |
| --- | --- |
| "userId" | 调用该方法的用户ID |
| "schemaCode" | 业务对象模式编码 |
| "objectId" | 业务对象的ID |
| "requireRelatedObjects" | 要求返回关联对象的头信息 |
| "fileTable" | 返回这个业务对象相关的附件的文件头，格式是(ObjectId + PropertyName, FileList) |
| "associatedBOHeaders" | 关联对象的头信息 |
| "unitNameTable" | BO相关的组织结构的ID和名称信息 |
| 返回值 |  |
| 执行的参数的返回值 |  |


方法名称 : GetBizObjectHeaders(System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{System.String}})

| 参数 | 说明 |
| --- | --- |
| "schemaIds" | 业务对象ID信息，格式是(SchemaCode, (BizObjectId)) |
| 返回值 |  |
| 返回(BizObjectId, BizObjectHeader) |  |


方法名称 : UpdateBizObject(System.String,System.String,H3.Data.Serialization.VirtualObject,System.String\[\],System.String@,System.String@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "userId" | 调用该方法的用户ID |
| "schemaCode" | 业务对象模式编码 |
| "obj" | 新的业务对象 |
| "members" | 更新该业务对象相关的人员 |
| "ownerId" | 如果该对象是继承权限，那么需要自动变更拥有者 |
| "ownerDeptId" | 如果该对象是继承权限，那么需要自动变更拥有者 |
| "errorMessage" | 异常信息 |
| 返回值 |  |
| |  |


方法名称 : RemoveBizObject(System.String,System.String,H3.DataModel.BizObjectType,System.String,System.Boolean,H3.DataModel.BizObjectHeader@)

| 参数 | 说明 |
| --- | --- |
| "userId" | 调用该方法的用户ID |
| "schemaCode" | 业务对象模式编码 |
| "bizObjectType" | 业务对象的类型，这个参数可以传，也可以不传，如果不传的话，可以输入Unspecified |
| "objectId" | 业务对象的ID |
| "checkReference" | 是否检查被其他对象引用 |
| "referredObjectHeader" | 引用该对象的对象的摘要信息 |
| 返回值 |  |
| |  |


方法名称 : Commit(H3.DataModel.BizObjectCommitRequest\[\])

| 参数 | 说明 |
| --- | --- |
| "requests" | |
| 返回值 |  |
| |  |


方法名称 : AddBizObject(System.String,System.String,H3.Data.Serialization.VirtualObject,System.String\[\],System.String@,System.String@,System.String@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "userId" | 调用该方法的用户ID |
| "schemaCode" | 业务对象模式编码 |
| "obj" | 要添加的业务对象 |
| "members" | 与这个业务对象相关的人员 |
| "objName" | 该对象的新名称，如果对象名称中包含了流水号，那么这里会重新计算对象名称 |
| "ownerId" | 如果该对象是继承权限，那么需要自动变更拥有者 |
| "ownerDeptId" | 如果该对象是继承权限，那么需要自动变更拥有者 |
| "errorMessage" | 异常信息 |
| 返回值 |  |
| 执行的参数的返回值 |  |


方法名称 : GetList(System.String,System.String,H3.DataModel.GetListScopeType,H3.Data.Filter.Filter,System.Int32@,System.Boolean,System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader}@,System.Collections.Generic.Dictionary{System.String,System.String}@)

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户ID |
| "schemaCode" | 数据模型编码 |
| "authScopeType" | 调用GetList的时候的数据权限过滤方式，比如：由我创建的、与我相关的等等 |
| "filter" | 过滤条件 |
| "count" | 获取集合数据量 |
| "requireRelatedObjects" | 要求返回关联对象的头信息 |
| "associatedBOHeaders" | 关联对象的头信息 |
| "unitNameTable" | 整个BO相关的组织结构的ID和名称信息 |
| 返回值 |  |
| 实体结构集合 |  |


方法名称 : GetListCount(System.String,H3.DataModel.BizObjectSchema,H3.DataModel.GetListScopeType,H3.Data.Filter.Filter)

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户ID |
| "schema" | 数据模型 |
| "authScopeType" | 调用GetList的时候的数据权限过滤方式，比如：由我创建的、与我相关的等等 |
| "filter" | 过滤条件 |
| 返回值 |  |
| |  |


方法名称 : QueryDataTable(System.String,System.String,H3.DataModel.GetListScopeType,H3.Data.Filter.Filter,System.Int32@,System.Boolean,System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader}@,System.Collections.Generic.Dictionary{System.String,System.String}@)

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户ID |
| "schemaCode" | 数据模型编码 |
| "authScopeType" | 调用GetList的时候的数据权限过滤方式，比如：由我创建的、与我相关的等等 |
| "filter" | 过滤条件 |
| "count" | 获取集合数据量 |
| "requireRelatedObjects" | 要求返回关联对象的头信息 |
| "associatedBOHeaders" | 关联对象的头信息 |
| "unitNameTable" | 整个BO相关的组织结构的ID和名称信息 |
| 返回值 |  |
| |  |


方法名称 : Clear(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 业务对象模式编码 |
| 返回值 |  |
| |  |


方法名称 : QueryFileHeader(System.String,System.String,System.String,System.String,H3.Data.BoolValue,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 业务对象模式编码 |
| "ChildSchemaCode" | |
| "bizObjectId" | 业务对象ID |
| "propertyName" | 属性名称 |
| "lastVersion" | 是否只查询最终版本 |
| "fileName" | 要查询的文件的名称，常用于查找同一个文件的不同版本 |
| 返回值 |  |
| 文件头信息，不包含文件内容 |  |


方法名称 : ExistFile(System.String,System.String,System.String,System.String,H3.Data.BoolValue,System.String)

| 参数 | 说明 |
| --- | --- |
| "SchemaCode" | 模型编码 |
| "ChildSchemaCode" | 子模型编码 |
| "PropertyName" | 属性名 |
| "BizObjectId" | 业务对象Id |
| "LastVersion" | 最后版本 |
| "FileName" | 文件名 |
| 返回值 |  |
| |  |


方法名称 : GetBizObjectFileHeaders(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "bizObjectIds" | 要查询的业务对象的ID |
| 返回值 |  |
| 业务对象的文件头 |  |


方法名称 : GetFileHeaders(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "fileIds" | 文件ID数组 |
| 返回值 |  |
| 文件头信息，不包含文件内容 |  |


方法名称 : GetFileHeader(System.String)

| 参数 | 说明 |
| --- | --- |
| "fileId" | 文件ID |
| 返回值 |  |
| 文件头信息，不包含文件内容 |  |


方法名称 : GetFile(System.String)

| 参数 | 说明 |
| --- | --- |
| "fileId" | 文件ID |
| 返回值 |  |
| 文件信息，包括文件内容 |  |


方法名称 : AddFile(H3.DataModel.BizObjectFile)

| 参数 | 说明 |
| --- | --- |
| "file" | 要添加的文件 |
| 返回值 |  |
| 如果添加成功则返回文件ID，否则返回null |  |


方法名称 : AddFiles(H3.DataModel.BizObjectFile\[\])

| 参数 | 说明 |
| --- | --- |
| "files" | 要添加的文件 |
| 返回值 |  |
| |  |


方法名称 : AttachBizObject(System.String\[\],System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "fileIds" | 要附加到业务对象的文件的列表 |
| "schemaCode" | 业务对象模式编码 |
| "childSchemaCode" | 子表业务对象模式编码 |
| "propertyName" | 业务对象属性名称 |
| "bizObjectId" | 业务对象ID |
| 返回值 |  |
| |  |


方法名称 : HandleBoFileEvent(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 表单编码 |
| "propertyName" | 属性编码 |
| "bizObjectId" | 业务对象ID |
| 返回值 |  |
| |  |


方法名称 : UpdateFile(System.String,System.String,System.String,System.String,System.Byte\[\],System.Int64)

| 参数 | 说明 |
| --- | --- |
| "fileId" | 文件ID |
| "modifiedBy" | 更新人 |
| "fileName" | 新文件名 |
| "contentType" | ContentType |
| "content" | 内容 |
| "fileFlag" | 文件的标签 |
| 返回值 |  |
| |  |


方法名称 : UpdateFileDecription(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "fileId" | 文件ID |
| "modifiedBy" | 更新人 |
| "Description" | 文件描述 |
| 返回值 |  |
| |  |


方法名称 : UpdateFileName(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "fileId" | 文件ID |
| "modifiedBy" | 更新人 |
| "fileName" | 文件名称 |
| 返回值 |  |
| |  |


方法名称 : CopyFiles(System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.Boolean,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "sourceSchemaCode" | 源业务对象模式 |
| "sourceChildSchemaCode" | |
| "sourceBizObjectId" | 源业务对象ID |
| "sourcePropertyName" | 源业务对象属性名称 |
| "destSchemaCode" | 目标业务对象模式编码 |
| "destChildSchemaCode" | |
| "destBizObjectId" | 目标业务对象ID |
| "destPropertyName" | 目标业务对象属性名称 |
| "overwrite" | 是否是覆盖目标业务对象属性 |
| "physicalRemove" | 如果是覆盖模式，那么这里记录是否物理删除目标业务对象属性上的文件 |
| 返回值 |  |
| 新建的文件的文件头信息 |  |


方法名称 : RemoveFile(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "fileId" | 附件ID |
| "physical" | 是否物理删除 |
| 返回值 |  |
| |  |


方法名称 : RemoveFilesByBizObjectProperty(System.String,System.String,System.String,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 业务对象模式编码 |
| "childSchemaCode" | 子业务对象模式编码 |
| "propertyName" | 属性编码 |
| "bizObjectId" | 业务对象ID |
| "physical" | 是否物理删除 |
| 返回值 |  |
| |  |


方法名称 : UpdateComment(System.String,System.String,System.String,System.String,System.String,System.String\[\],H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 数据模型编码 |
| "objectId" | 数据实体ID |
| "commentId" | 审批意见ID |
| "text" | 新的审批意见值 |
| "signature" | 电子签章 |
| "attachmentIds" | 附件 |
| "approval" | 新的审批结果 |
| 返回值 |  |
| 如果成功则返回Success，否则返回错误代码 |  |


方法名称 : AddComment(H3.DataModel.Comment)

| 参数 | 说明 |
| --- | --- |
| "comment" | 审批意见对象 |
| 返回值 |  |
| 如果成功则返回Success，否则返回错误代码 |  |


方法名称 : AddComments(H3.DataModel.Comment\[\])

| 参数 | 说明 |
| --- | --- |
| "comments" | 审批意见集合 |
| 返回值 |  |
| |  |


方法名称 : GetCommentsByWorkflowInstance(System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 数据模型编码 |
| "bizObjectId" | 数据实体ID |
| "workflowInstanceId" | 流程实例ID |
| "userId" | 用户ID |
| "activity" | 活动节点编码 |
| 返回值 |  |
| 审批意见集合 |  |


方法名称 : GetCommentsByBizObject(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 数据模型编码 |
| "bizObjectId" | 数据实体ID |
| 返回值 |  |
| 审批意见集合 |  |


方法名称 : CopyComments(System.String,System.String,System.String,System.String,System.String,System.String,System.Int32,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "sourceSchemaCode" | 源数据模型编码 |
| "sourceBizObjectId" | 源数据模型ID |
| "sourceInstanceId" | 源流程实例ID |
| "destSchemaCode" | 目标数据模型编码 |
| "destBizObjectId" | 目标数据模型ID |
| "destInstanceId" | 目标流程实例ID |
| "destTokenId" | 目标活动节点ID |
| "overwrite" | 是否覆盖模式 |
| 返回值 |  |
| |  |


方法名称 : UpdateProperties(System.String,System.String,System.String\[\],System.Collections.Generic.Dictionary{System.String,System.Object})

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户ID |
| "schemaCode" | 业务对象模式的编码 |
| "objectIds" | 业务对象ID |
| "properties" | 要更新的属性 |
| 返回值 |  |
| |  |


方法名称 : AddBizObjectAcl(H3.Acl.BizObjectFolderAcl)

| 参数 | 说明 |
| --- | --- |
| "acl" | 数据模型权限对象 |
| 返回值 |  |
| 返回更新是否成功 |  |


方法名称 : UpdateBizObjectAcl(H3.Acl.BizObjectFolderAcl)

| 参数 | 说明 |
| --- | --- |
| "acl" | 数据模型权限对象 |
| 返回值 |  |
| |  |


方法名称 : RemoveBizObjectAcl(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 数据模型编码 |
| "folderId" | 文件夹ID |
| "aclId" | 权限ID |
| 返回值 |  |
| |  |


方法名称 : GetBizObjectAcls(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 数据模型编码 |
| "folderId" | 文件夹ID |
| 返回值 |  |
| 返回权限对象的集合 |  |


方法名称 : GetBizObjectAcl(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 数据模型编码 |
| "folderId" | 文件夹ID |
| "aclId" | 权限ID |
| 返回值 |  |
| 返回业务权限对象 |  |


方法名称 : GetBizObjectUserAcls(System.String,System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 数据模型编码 |
| "folderId" | 文件夹ID |
| "users" | 用户集合 |
| 返回值 |  |
| 返回权限对象的集合 |  |


方法名称 : CheckSchemaCodeDuplicated(System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 数据模型编码 |
| "message" | 错误信息 |
| 返回值 |  |
| 重复返回false，没重复返回true |  |


方法名称 : HandOver(System.String,System.String,System.String\[\],System.String@)

| 参数 | 说明 |
| --- | --- |
| "sourceUserId" | 任务源用户ID |
| "targetUserId" | 任务目标用户ID |
| "schemaCodes" | 业务对象模式编码 |
| "errorMsg" | 错误信息 |
| 返回值 |  |
| |  |


方法名称 : LoadAssociations(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| 返回值 |  |
| |  |


方法名称 : LoadAssociationsForFormula(System.String,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{H3.DataModel.LiteProperty}}@,System.Collections.Generic.Dictionary{System.String,System.String}@,System.Collections.Generic.Dictionary{System.String,System.String}@,System.Collections.Generic.List{H3.DataModel.LiteProperty}@)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| "associationProperties" | |
| "associations" | |
| "associationBONames" | |
| "canUpdateProperties" | |
| 返回值 |  |

方法名称 : GetCommentSignature(comments\[0\].Signature)

| 参数 |
| --- |
| "commentid" |
| 返回值 |