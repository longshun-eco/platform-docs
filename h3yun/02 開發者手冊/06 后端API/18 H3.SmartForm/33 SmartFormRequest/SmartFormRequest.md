---
title: "SmartFormRequest"
source: "https://help.h3yun.com/contents/593/656.html"
category: "開發者手冊 / 后端API / H3.SmartForm / SmartFormRequest"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : SmartFormRequest
说明 : 表单环境，用于获得各项工作流服务，当前表单的工作模式和流程数据 属性 : 

| 名称 | 说明 |
| --- | --- |
| Authorized | 是否授权 |
| Message | 错误信息 |
| Valid | 是否通过请求验证 |
| AppCode | 应用编码 |
| NodeType | 表单的菜单类型 |
| Javascript | Javascript脚本 |
| IsCustom | 是否自定义 |
| IsSass | 是否sass |
| ModifiedTime | 修改时间 |
| AssociationLists | 关联列表 |
| FormMode | 打开表单所使用的模式，比如：只读模式、打印模式、工作模式等，如果URL参数中未指定，则默认为Unspecified，由表单程序自行指定 |
| SharingKey | 共享标示 |
| FormDataType | 获取平台模式(流程/开发平台) |
| WorkItemId | 获取当前表单对应的工作任务ID |
| WorkItem | 获取当前任务 |
| InstanceId | 当前表单对应的流程实例ID |
| WorkflowInstance | 当前表单对应的流程实例的上下文 |
| WorkflowVersion | 当前表单对应的流程模板版本 |
| WorkflowTemplate | 当前表单对应的流程模板 |
| Schema | 获取或设置数据模型结构 |
| SchemaCode | 获取或设置数据模型编码 |
| IsExternalForm | 是否表单外链 |
| FormSetting | 获取当前显示的表单 |
| FormDisplayName | 获取或设置当前表单的显示名称 |
| BizObjectId | 获取或设置数据实例ID |
| ActivityCode | 当前活动的名称。如果是发起模式，那么返回第一个活动的名称；如果是工作项相关的模式，那么返回工作项对应的活动名称；否则从URL里面读取。 |
| ActivityTemplate | 获取当前活动对应的活动模板 |
| BizObject | 获取当前业务实例对象 |
| FormData | 用于获得/设置流程数据的属性，包括值。该对象缓存在this.\_InstanceData中，当页面PostBack的时候需要重新创建。 InstanceData启用缓存机制，也就是说，对于任意一个数据项的修改，并不会直接回写到服务器一，只有等到调用InstanceData.Submit方法之后，才会更新服务器；同时，读取一个只得时候也只会从缓存中读取，只有无法读到，才从服务器上请求。 |
| IsWorkMode | 当前表单模式是否是工作模式 |
| IsCreateMode | 当前表单模式是否是发起模式 |
| Readonly | 当前表单模式是否是查看模式(查看模式表单只允许只读) |
| ParticipantId | 获取当前登录用户的ID |
| ParticipantParentId | 获取当前任务处理用户所在的组织ID |
| Participant | 获取当前用户的访问对象，通过该对象可以获得当前用户的所有信息，包括：所属的组织结构、权限等。 |
| DataDictItems | 字段绑定的数据字典 |
| FileList | 文件列表 |
| QrCodeUrl | 二维码链接 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| Param\_Mode | 表单URL上的参数，用于指定打开表单所使用的模式，比如：只读模式、打印模式、工作模式等 |
| Param\_SchemaCode | 表单上模式编码参数 |
| Param\_BizObjectId | 表单上业务对象ID参数 |
| Param\_WorkItemId | 表单URL上的参数，如果是以打开一个工作项的角度来打开这个表单的话，那么需要指定该参数 |
| Param\_InstanceId | 表单URL上的参数，如果是以打开一个流程的表单的角度来打开这个表单的话，那么需要指定该参数 |
| Param\_WorkflowVersion | 表单URL上的参数，流程发起时有效，用于指定当前表单对应的流程模板。实际上，一个表单可以被N个流程模板/版本共用。 |
| Param\_LoginName | 表单URL上的参数，用于指定当前用户名，这样用户不用登陆即可直接打开表单 |
| Param\_LoginPassword | 表单URL上的参数，用于指定当前用户的密码，这样用户不用登陆即可直接打开表单 |
| Param\_Method | 表单URL上的参数，用于传递业务对象的 Method Name |
| Param\_IsMobile | 是否通过手机访问的 |
| Param\_SharingKey | 共享标示 |
| Param\_EngineCode | 引擎编码 |
| Param\_AttachmentId | 附件ID |
| Param\_IsExternalForm | 是否表单外链 |
| \_FormDataType | 平台模式 |


构造方法名称 : #ctor(H3.IEngine,H3.Web.UserContext,System.Collections.Generic.Dictionary{System.String,System.String},System.String)

| 参数 | 说明 |
| --- | --- |
| "engine" | 引擎实例对象 |
| "userContext" | 当前用户的上下文 |
| "valueTable" | 参数值表 |
| "schemaCode" | 业务对象模式编码 |
| 返回值 |  |
| |  |


构造方法名称 : #ctor(H3.Web.UserContext,System.Collections.Generic.Dictionary{System.String,System.String},System.String,System.Boolean,System.String,H3.IEngine)

| 参数 | 说明 |
| --- | --- |
| "userContext" | 用户上下文信息 |
| "valueTable" | 请求参数集合 |
| "appCode" | 应用编码 |
| "IsCustom" | 是否自定义 |
| "schemaCode" | 表单编码 |
| "engine" | 引擎实例 |
| 返回值 |  |
| |  |


方法名称 : Initialize

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetRequestParameters

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 返回参数数据字典 |  |


方法名称 : ParseDefinedParticipants(System.String)

| 参数 | 说明 |
| --- | --- |
| "ActivityCode" | 活动编码 |
| 返回值 |  |
| 实际的处理人，这个会具体落实到组织结构里的某个/某些人 |  |


方法名称 : ParseDefinedWorkflowParticipants

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 实际的处理人，这个会具体落实到组织结构里的某个/某些人 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | |
| 返回值 |  |
| |
 |