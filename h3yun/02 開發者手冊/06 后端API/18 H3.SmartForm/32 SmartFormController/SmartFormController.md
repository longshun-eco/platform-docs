---
title: "SmartFormController"
source: "https://help.h3yun.com/contents/592/651.html"
category: "開發者手冊 / 后端API / H3.SmartForm / SmartFormController"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : SmartFormController
说明 : 表单的控制器，用于控制表单的提交和展示 属性 : 

| 名称 | 说明 |
| --- | --- |
| Request | 请求的上下文 |
| ClientActivity | 当前活动 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| Button\_Edit | 编辑 |
| Button\_Submit | 提交 |
| Button\_SubmitAndAdd | 提交并添加:PC端有提交时，出现该按钮 |
| Button\_Read | 已阅 |
| Button\_Reject | 驳回 |
| Button\_Save | 保存 |
| Button\_Remove | 删除 |
| Button\_Close | 关闭 |
| Button\_Print | 打印 |
| Button\_ViewInstance | 流程状态 |
| Button\_FinishInstance | 结束流程 |
| Button\_CancelInstance | 作废流程 |
| Button\_RetrieveInstance | 取回流程 |
| Button\_Forward | 转发 |
| Button\_LinkToSns | 链接到评论 |
| RejectTo\_Start | 驳回到开始 |
| RejectTo\_Previous | 驳回到前一步 |
| Button\_ViewQrCode | 查看二维码 |
| Param\_PostValue | 页面传递过来的值 |
| FormDisplayName | 增加表单名称数据项 |
| DataItem\_CreatedByFullName | 创建人的全名 |
| Action\_LoadBoListHeader | 加载BO对象的列表头 |
| Action\_LoadBoListData | 加载BO对象的列表数据 |
| Action\_LoadSNSPost | 加载社交评论 |
| Action\_OnWorkflowInstanceStateChanged | 流程状态变更事件 |
| DefaultApproveText | 默认的审批同意意见 |
| DefaultDisapproveText | 默认的审批不同意意见 |


构造方法名称 : #ctor(H3.SmartForm.SmartFormRequest)

| 参数 | 说明 |
| --- | --- |
| "request" | 请求的上下文 |
| 返回值 |  |
| |  |


方法名称 : OnAction(System.String,System.Object,H3.Workflow.Instance.WorkflowInstanceState,H3.Workflow.Instance.WorkflowInstanceState)

| 参数 | 说明 |
| --- | --- |
| "actionName" | 操作的编码 |
| "postValue" | 请求回传回来的数据 |
| "oldState" | 处理前的状态 |
| "newState" | 处理后的状态 |
| 返回值 |  |
| 响应的上下文 |  |


方法名称 : Load

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 表单的数据响应 |  |


方法名称 : OnLoad(H3.SmartForm.LoadSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "response" | 表单加载出来的数据的上下文 |
| 返回值 |  |
| |  |


方法名称 : ValidateAuthorization

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 用户是否有操作权限 |  |


方法名称 : LoadBizObjectArrayData(H3.DataModel.PropertySchema,H3.DataModel.PropertyState,System.Boolean,System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit},System.Boolean@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "proertySchema" | 对象字段 |
| "fieldState" | 字段状态 |
| "formLocked" | 表单是否锁住 |
| "unitTable" | id与组织机构单元 |
| "formEditable" | 表单是否可编辑 |
| "errorMessage" | 错误信息 |
| 返回值 |  |
| 业务对象数组数据 |  |


方法名称 : LoadBizObjectData(H3.DataModel.PropertySchema,H3.DataModel.PropertyState,System.Boolean,System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit})

| 参数 | 说明 |
| --- | --- |
| "propertySchema" | 字段属性 |
| "fieldState" | 字段状态 |
| "formLocked" | 表单锁状态 |
| "unitTable" | id与组织单元表 |
| 返回值 |  |
| 返回字段数据 |  |


方法名称 : LoadBizObjectProperty(H3.DataModel.PropertySchema,H3.DataModel.PropertyState,H3.DataModel.PropertySchema,H3.DataModel.BizObject,System.Collections.Generic.Dictionary{System.String,H3.Organization.Unit})

| 参数 | 说明 |
| --- | --- |
| "propertySchema" | 业务对象数组(父对象)属性 |
| "fieldState" | 业务对象字段状态 |
| "childPropertySchema" | 字段属性 |
| "childObj" | 业务对象实例 |
| "unitTable" | id与组织单元表 |
| 返回值 |  |
| 返回从控件属性构造的MVC数据项 |  |


方法名称 : IsRetrievable(H3.Workflow.Template.ParticipativeActivity)

| 参数 | 说明 |
| --- | --- |
| "activity" | 活动 |
| 返回值 |  |
| 是否允许被取回 |  |


方法名称 : LoadCommentData

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 审批控件数据 |  |


方法名称 : LoadBoListHeader(System.String,H3.SmartForm.SmartFormPostValue,H3.SmartForm.SubmitSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "actionName" | 当前操作的编码 |
| "postValue" | 客户端post的数据 |
| "response" | 返回客户端的数据 |
| 返回值 |  |
| |  |


方法名称 : LoadBoListData(System.String,H3.SmartForm.SmartFormPostValue,H3.SmartForm.SubmitSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "actionName" | 当前操作的编码 |
| "postValue" | 客户端POST数据 |
| "response" | 返回客户端的数据 |
| 返回值 |  |
| |  |


方法名称 : Submit(System.String,H3.SmartForm.SmartFormPostValue,H3.SmartForm.SubmitSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "actionName" | 操作编码 |
| "postValue" | 请求的参数 |
| "response" | 返回到表单的数据 |
| 返回值 |  |
| |  |


方法名称 : OnSubmit(System.String,H3.SmartForm.SmartFormPostValue,H3.SmartForm.SubmitSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "actionName" | 当前操作编码 |
| "postValue" | 操作的数据 |
| "response" | 返回的数据 |
| 返回值 |  |
| |  |


方法名称 : RemoveBizObjectAndInstance(H3.SmartForm.SmartFormPostValue,H3.SmartForm.SubmitSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "postValue" | 传入数据 |
| "response" | 返回值 |
| 返回值 |  |
| |  |


方法名称 : Retrieve(H3.SmartForm.SubmitSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "response" | 返回客户端的数据 |
| 返回值 |  |
| |  |


方法名称 : GetPostTokenId(H3.SmartForm.SubmitSmartFormResponse,System.Int32,System.Int32@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "response" | 返回客户端的数据 |
| "currentTokenId" | 当前步骤ID |
| "postTokenId" | 后置步骤ID |
| "activity" | 活动编码 |
| 返回值 |  |
| 是否成功 |  |


方法名称 : SubmitWorkItem(H3.SmartForm.SmartFormPostValue,H3.Data.BoolValue,H3.Workflow.WorkItem.ActionEventType)

| 参数 | 说明 |
| --- | --- |
| "postValue" | 表单传递过来的值 |
| "approval" | 审核结果 |
| "actionEventType" | 事件类型 |
| 返回值 |  |
| 需要变更的流程实例 |  |


方法名称 : GetPreToken(System.Int32)

| 参数 | 说明 |
| --- | --- |
| "tokenId" | 步骤ID |
| 返回值 |  |
| 步骤信息 |  |


方法名称 : GetPreToken(H3.Workflow.Instance.IToken)

| 参数 | 说明 |
| --- | --- |
| "token" | 步骤 |
| 返回值 |  |
| 前驱活动 |  |


方法名称 : ValidateData(H3.SmartForm.SmartFormPostValue,H3.SmartForm.SubmitSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "postValue" | 客户端请求的数据 |
| "response" | 返回客户端的数据 |
| 返回值 |  |
| 数据是否合法 |  |


方法名称 : ValidateBizObject(System.Collections.Generic.IDictionary{System.String,System.Object},H3.DataModel.PropertySchema,H3.SmartForm.SubmitSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "postData" | 客户端的数据 |
| "propertySchema" | 字段属性 |
| "response" | 返回的数据 |
| 返回值 |  |
| 业务对像数据是否合法 |  |


方法名称 : ValidateBizObjectArray(System.Collections.Generic.IDictionary{System.String,System.Object},H3.DataModel.PropertySchema,H3.SmartForm.SubmitSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "postData" | 请求数据集合 |
| "field" | 字段 |
| "response" | 引擎返回准备传输到前台的表单数据 |
| 返回值 |  |
| 业务对象数组数据是否合法 |  |


方法名称 : ValidateRealType(System.Object,System.Type)

| 参数 | 说明 |
| --- | --- |
| "value" | 数据 |
| "realType" | 数据类型 |
| 返回值 |  |
| 是否可以转换为真实数据类型 |  |


方法名称 : SetUneditableValue(H3.DataModel.PropertySchema,H3.DataModel.BizObjectSchema,System.Collections.Generic.IDictionary{System.String,System.Object},System.Collections.Generic.List{H3.SmartForm.FileItem},System.Collections.Generic.Dictionary{System.String,System.String})

| 参数 | 说明 |
| --- | --- |
| "propertySchema" | 字段属性 |
| "schema" | 表单编码 |
| "postData" | 请求数据 |
| "fileList" | 附件列表 |
| "parentSchemaCodes" | 父级schema编码集合 |
| 返回值 |  |
| |  |


方法名称 : WritePostValueToBizObject(System.String,H3.SmartForm.SmartFormPostValue,H3.Data.BoolValue,H3.SmartForm.SubmitSmartFormResponse)

| 参数 | 说明 |
| --- | --- |
| "actionName" | 当前操作的编码 |
| "postValue" | 客户端的数据 |
| "approval" | 是否同意 |
| "response" | 返回客户端的数据 |
| 返回值 |  |
| |  |


方法名称 : SaveBizObject(System.Collections.Generic.IDictionary{System.String,System.Object},H3.DataModel.PropertySchema,System.Collections.Generic.List{H3.SmartForm.FileItem})

| 参数 | 说明 |
| --- | --- |
| "postData" | 客户端数据 |
| "propertySchema" | 字段属性 |
| "fileList" | 文件列表 |
| 返回值 |  |
| |  |


方法名称 : SaveBizObjectArray(System.Collections.Generic.IDictionary{System.String,System.Object},H3.DataModel.PropertySchema,System.Collections.Generic.List{H3.SmartForm.FileItem})

| 参数 | 说明 |
| --- | --- |
| "postData" | 需要保存的数据 |
| "propertySchema" | 字段属性 |
| "fileList" | 文件ID列表（需要删除和添加） |
| 返回值 |  |
| |  |


方法名称 : GetColumnVisible(System.String,H3.DataModel.PropertySchema)

| 参数 | 说明 |
| --- | --- |
| "columnName" | 字段编码 |
| "propertySchema" | 字段属性 |
| 返回值 |  |
| 字段是否可见 |  |


方法名称 : GetColumnEditable(System.String,H3.DataModel.PropertySchema)

| 参数 | 说明 |
| --- | --- |
| "columnName" | 字段编码 |
| "propertySchema" | 字段属性 |
| 返回值 |  |
| 字段是否可编辑 |  |


方法名称 : UpdateBo(System.Collections.Generic.Dictionary{System.String,System.Object},H3.DataModel.BizObject,H3.DataModel.PropertySchema,System.Collections.Generic.List{H3.SmartForm.FileItem})

| 参数 | 说明 |
| --- | --- |
| "nameValues" | 需要更新的属性键值对 |
| "obj" | 业务对象 |
| "propertySchema" | 字段属性 |
| "fileList" | 附件ID列表 |
| 返回值 |  |
| |  |


方法名称 : GetBoList(H3.DataModel.PropertySchema)

| 参数 | 说明 |
| --- | --- |
| "propertySchema" | 字段属性 |
| 返回值 |  |
| BO列表 |  |


方法名称 : GetBoValues(H3.DataModel.BizObject,H3.DataModel.PropertySchema)

| 参数 | 说明 |
| --- | --- |
| "obj" | 业务对象 |
| "propertySchema" | 字段属性 |
| 返回值 |  |
| 业务对象数组 |  |


方法名称 : HandleWorkflowInstanceChange(H3.Workflow.Messages.WorkflowInstanceChangeSet)

| 参数 | 说明 |
| --- | --- |
| "changeSet" | 需要变更的流程实例 |
| 返回值 |  |
| |  |


方法名称 : OnWorkflowInstanceStateChanged(H3.Workflow.Instance.WorkflowInstanceState,H3.Workflow.Instance.WorkflowInstanceState)

| 参数 | 说明 |
| --- | --- |
| "oldState" | 改变前状态 |
| "newState" | 改变后状态 |
| 返回值 |  |
| |  |


方法名称 : OnWorkflowInstanceFinished

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : OnWorkflowInstanceCanceled

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |
 |