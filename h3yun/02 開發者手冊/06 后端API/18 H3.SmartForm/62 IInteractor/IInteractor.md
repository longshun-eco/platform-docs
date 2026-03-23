---
title: "IInteractor"
source: "https://help.h3yun.com/contents/622/809.html"
category: "開發者手冊 / 后端API / H3.SmartForm / IInteractor"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : IInteractor
说明 : 交互管理器，为了加速用户的交互，在这里将很多的接口进行汇总，一次性返回所有请求的数据 
方法名称 : LoadUser(H3.Organization.User@,H3.Organization.OrgRole\[\]@,H3.Organization.OrgPost\[\]@,System.String\[\]@,System.Boolean@,System.Collections.Generic.HashSet{System.String}@,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{System.String}}@,H3.Organization.Unit\[\]@,System.String\[\]@,System.Collections.Generic.Dictionary{System.String,System.Object}@,H3.Organization.UserRecentActivity@,System.Collections.Generic.Dictionary{System.String,System.String}@,System.Collections.Generic.Dictionary{System.String,System.String\[\]}@,System.Collections.Generic.Dictionary{System.String,System.String\[\]}@,System.Collections.Generic.Dictionary{System.String,H3.App.AppSolution}@,H3.Data.FileServiceType@)

| 参数 | 说明 |
| --- | --- |
| "user" | 输出用户对象 |
| "roles" | 用户所属于的角色 |
| "posts" | 用户所属于的岗位 |
| "recursiveMemberOfs2" | 输出用户的上级单位集合 |
| "isAdministrator" | 输出是否管理员 |
| "functionNodeTable" | 输出有权限的节点集合 |
| "functionScopeTable" | (FunctionCode.ToLower(), (Unit))，该用户针对某个功能可以访问的组织机构的列表 |
| "memberOfUnits" | 输出子成员对象 |
| "recursiveOwnParents" | 获得用户的所有隶属于部门 |
| "portalSettings" | 输出页面配置属性集合 |
| "recent" | 用户的最近访问 |
| "workflowNames" | 流程名称 |
| "formActionCodeTable" | |
| "listViewActionCodeTable" | |
| "solutionStatus" | 解决方案状态 |
| "fileServiceType" | 附件类型 |
| 返回值 |  |
| 如果用户存在，则返回true，否则返回false |  |


方法名称 : LoadData(H3.SmartForm.SmartFormMode,System.String,System.Int32,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.Boolean,H3.SmartForm.SmartFormDataType@,H3.SmartForm.SmartFormMode@,H3.Data.BoolValue@,System.String@,H3.Workflow.Instance.WorkflowInstance@,H3.Workflow.WorkItem.WorkItem@,System.String@,H3.SNS.SNSSharingItem@,H3.Data.Serialization.VirtualObject@,System.Boolean,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{H3.DataModel.BizObjectFileHeader}}@,System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader}@,System.Collections.Generic.Dictionary{System.String,System.String}@,System.Collections.Generic.List{H3.Data.DataDictItem}@,System.String@,System.Collections.Generic.Dictionary{System.String,System.String}@,System.Boolean@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "formMode" | 操作模式 |
| "schemaCode" | 业务对象模式编码 |
| "workflowVersion" | 流程版本 |
| "instanceId" | 流程实例ID |
| "workItemId" | 任务ID |
| "bizObjectId" | 业务对象模式Id |
| "sharingKey" | |
| "userId" | 当前用户ID |
| "userHostAddress" | 用户的IP地址 |
| "platform" | 用户使用的操作系统 |
| "browser" | 用户使用的浏览器 |
| "isExternalForm" | |
| "formDataType" | |
| "formMode2" | |
| "authorized" | 输出权限认证是否成功 |
| "workflowInstance" | 输出流程实例数据 |
| "WorkItem" | 输出工作任务对象 |
| "activityCode" | 输出活动编码 |
| "formDisplayName" | 输出获取表单显示名称 |
| "sharingItem" | |
| "virtualObject" | |
| "requireRelatedObjects" | |
| "fileTable" | |
| "associatedBOHeaders" | |
| "unitNameTable" | |
| "dataDictItems" | |
| "message" | 输出返回消息 |
| "AssociationLists" | |
| "hasAuthority" | |
| "qrCodeUrl" | |
| 返回值 |  |
| 获取是否成功 |  |


方法名称 : OriginateInstance(System.String,System.String,System.Int32,System.String,System.String,H3.Workflow.WorkItem.AccessMethod,System.Boolean,System.String,System.Boolean,System.String@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户ID |
| "schemaCode" | 数据模型编码 |
| "bizObjectId" | 数据模型实例ID |
| "workflowVersion" | 流程模板版本号 |
| "instanceId" | 流程实例ID |
| "accessPoint" | 接入方式 |
| "finishStartActivity" | 是否自动提交第一个活动 |
| "destActivityCode" | 自动节点第一个活动后的目标活动节点 |
| "ReturnWorkItem" | |
| "WorkItemId" | |
| "ErrorMessage" | |
| 返回值 |  |
| 返回流程的状态，可能是多条流程的状态 |  |


方法名称 : FinishWorkItem(System.String,System.String,H3.Workflow.WorkItem.AccessMethod,H3.Data.BoolValue,System.String,System.String,H3.Workflow.WorkItem.ActionEventType,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "WorkItemId" | 工作任务ID |
| "UserId" | 用户ID |
| "AccessPoint" | 接入方式 |
| "Approval" | 审核结果 |
| "Comment" | 审核意见 |
| "ActionName" | 操作按钮名称 |
| "ActionEventType" | 操作事件类型 |
| "DestActivityCode" | 目标节点编码 |
| "ClientAddress" | 客户端IP地址 |
| "ClientPlatform" | 客户端平台类型 |
| "ClientBrowser" | 客户端浏览器类型 |
| 返回值 |  |
| |  |


方法名称 : UpdateFiles(System.String,System.String,System.String,System.String,System.String,System.String\[\],System.String\[\],System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "UserId" | 当前用户的ID |
| "SchemaCode" | 业务对象编码 |
| "ChildSchemaCode" | 业务对象的子业务对象的编码 |
| "PropertyName" | 属性名称 |
| "BizObjectId" | 业务对象的ID |
| "AttachingFiles" | 新上传的需要绑定的文件 |
| "RemovingFiles" | 要删除的文件 |
| "Trackable" | 是否记录痕迹 |
| 返回值 |  |
| |  |


方法名称 : DeleteBizObjects(System.String,System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "UserId" | 请求删除业务对象的用户ID |
| "SchemaCode" | 业务对象模式编码 |
| "BizObjectIds" | 要删除的业务对象的ID |
| 返回值 |  |
| 删除失败的业务对象的ID |  |


方法名称 : LoadFormHomeData(System.String,System.String,System.String,System.String@,System.String@,System.Collections.Generic.List{H3.SmartForm.AssociationListSummary}@,System.Boolean@,System.Boolean@,System.Int32@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 表单code |
| "objectId" | 表单id |
| "userId" | 用户id |
| "name" | 名字 |
| "summary" | 摘要 |
| "associatedBos" | 关联列表 |
| "enableFormSns" | 是否显示动态 |
| "enableTask" | 是否启用任务提醒 |
| "taskCount" | |
| "iconId" | |
| 返回值 |  |
| 错误信息 |  |


方法名称 : LoadAssociationItemsCount(System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "userId" | |
| "sheetCode" | |
| "objectId" | |
| "associationSchemaCode" | |
| "propertyName" | |
| 返回值 |  |
| |  |


方法名称 : QueryMenus(System.String,System.String,H3.App.FunctionNode\[\],System.Collections.Generic.List{H3.SmartForm.ReportData}@,System.Collections.Generic.List{H3.SmartForm.MenuData}@)

| 参数 | 说明 |
| --- | --- |
| "Code" | 应用code |
| "UserID" | 用户名 |
| "Nodes" | 节点类型 |
| "ReportWidgets" | 报表页 |
| "RecentModule" | 最近活动模块 |
| 返回值 |  |
| 结果 |  |


方法名称 : QueryHomeReports(System.String,H3.App.FunctionNode\[\],System.Collections.Generic.List{H3.SmartForm.ReportData}@)

| 参数 | 说明 |
| --- | --- |
| "UserID" | |
| "Nodes" | |
| "ReportWidgets" | |
| 返回值 |  |
| |  |


方法名称 : QuerySolutionReports(System.String,System.Collections.Generic.List{H3.SmartForm.MenuData},System.Collections.Generic.List{H3.SmartForm.ReportData}@)

| 参数 | 说明 |
| --- | --- |
| "UserID" | |
| "Apps" | |
| "ReportWidgets" | |
| 返回值 |  |
| |  |


方法名称 : QuerySingleAppReports(System.String,System.String,System.Collections.Generic.List{H3.SmartForm.ReportData}@)

| 参数 | 说明 |
| --- | --- |
| "UserID" | |
| "appCode" | |
| "ReportWidgets" | |
| 返回值 |  |
| |  |


方法名称 : QuerySingleAppReportsAndTotalTasks(System.String,System.String,System.String\[\],System.String\[\],System.Boolean,System.Collections.Generic.List{H3.SmartForm.ReportData}@,System.Int32@,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "UserID" | |
| "appCode" | |
| "workflowSchemaCodes" | |
| "schemaCodes" | |
| "loadTasks" | |
| "ReportWidgets" | |
| "workflowsCount" | |
| "tasksCount" | |
| 返回值 |  |
| |  |


方法名称 : GetSolutionReportsAndWorkflowTaskCount(System.String,System.Collections.Generic.List{H3.SmartForm.MenuData},System.String\[\],System.Collections.Generic.List{H3.SmartForm.ReportData}@,System.Int32@,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "UserID" | |
| "Apps" | |
| "schemaCodes" | |
| "ReportWidgets" | |
| "workflowsCount" | |
| "tasksCount" | |
| 返回值 |  |
| |  |


方法名称 : GetHomeReportsAndWorkflowTaskCount(System.String,H3.App.FunctionNode\[\],System.Collections.Generic.List{H3.SmartForm.ReportData}@,System.Int32@,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "UserID" | 用户id |
| "Nodes" | 菜单集合 |
| "ReportWidgets" | 报表数据 |
| "workflowsCount" | 流程待办总数 |
| "tasksCount" | 任务待办总数 |
| 返回值 |  |
| |  |


方法名称 : GetHomeDatas(System.String,System.String,System.String\[\],System.Collections.Generic.List{H3.SmartForm.ReportData}@,System.String\[\]@)

| 参数 | 说明 |
| --- | --- |
| "userId" | |
| "solutionCode" | |
| "apps" | |
| "reportWidgets" | |
| "favoriteNodes" | |
| 返回值 |  |
| |  |


方法名称 : AddUserFavoriteFunction(System.String,H3.Organization.UserFavoriteFunction)

| 参数 | 说明 |
| --- | --- |
| "userId" | |
| "function" | |
| 返回值 |  |
| |  |


方法名称 : UpdateUserFavoriteFunction(System.String,H3.Organization.UserFavoriteFunction)

| 参数 | 说明 |
| --- | --- |
| "userId" | |
| "function" | |
| 返回值 |  |
| |  |


方法名称 : GetSolutionSchemaCodes(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | |
| 返回值 |  |
| |  |


方法名称 : GetSolutionCodeNames(System.String,System.Collections.Generic.List{System.String}@,System.Collections.Generic.Dictionary{System.String,System.String}@)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | |
| "schemaCodes" | |
| "codeNames" | |
| 返回值 |  |
| |  |


方法名称 : HandOver(System.String,System.String,System.String\[\],System.String@)

| 参数 | 说明 |
| --- | --- |
| "sourceUserId" | 任务源用户ID |
| "targetUserId" | 任务目标用户ID |
| "schemaCodes" | |
| "errorMsg" | 错误消息 |
| 返回值 |  |
| |  |


方法名称 : LoadSchemaCodes(System.String,System.String,System.Collections.Generic.Dictionary{System.String,System.String}@,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.Dictionary{System.String,System.String}}@)

| 参数 | 说明 |
| --- | --- |
| "SourceUserID" | 任务交接人 |
| "TargetUserID" | 任务接收人 |
| "DicParentCode" | |
| "DicParentAndChildren" | |
| 返回值 |  |
| |  |


方法名称 : LoadBizObject(System.String,System.String,System.String,System.Boolean,System.String@,H3.DataModel.BizObjectSchema@,H3.Data.Serialization.VirtualObject@,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{H3.DataModel.BizObjectFileHeader}}@,System.Collections.Generic.Dictionary{System.String,H3.DataModel.BizObjectHeader}@,System.Collections.Generic.Dictionary{System.String,System.String}@)

| 参数 | 说明 |
| --- | --- |
| "userId" | |
| "schemaCode" | |
| "objectId" | |
| "requireRelatedObjects" | |
| "userParentId" | |
| "schema" | |
| "virtualObj" | |
| "fileTable" | |
| "associatedBOHeaders" | |
| "unitNameTable" | |
| 返回值 |  |
| |  |


方法名称 : LoadListViewSetting(System.String,System.String,System.String,System.String,System.Collections.Generic.Dictionary{System.String,System.Object},System.Boolean,H3.Data.Filter.Filter@,System.Boolean@,H3.DataModel.PropertySchemaSummary@,System.Boolean@)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| "dataField" | |
| "sheetCode" | |
| "userId" | |
| "sheetData" | |
| "isDesignMode" | |
| "Filter" | |
| "HasAssociation" | |
| "Associationproperty" | |
| "IsDataAclScopeTypeAll" | |
| 返回值 |  |
| |  |


方法名称 : UpdateAppModule(H3.App.FunctionNode,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "functionNode" | |
| "validateSchema" | |
| 返回值 |  |
| |  |


方法名称 : AddExceptionLog(H3.Clusterware.Log.ExceptionLog)

| 参数 | 说明 |
| --- | --- |
| "log" | 异常日志 |
| 返回值 |  |
| |  |


方法名称 : ListViewLoadData(System.Boolean,System.String,System.String,System.Boolean,System.Boolean,H3.Data.Filter.Filter,System.String,H3.DataModel.GetListScopeType,System.Boolean,System.String,H3.Data.Filter.SortDirection,System.Int32@,System.Collections.Generic.List{System.Collections.Generic.Dictionary{System.String,System.Object}}@,System.Collections.Generic.Dictionary{System.String,System.Collections.Generic.List{H3.SmartForm.WorkflowParticipantInfo}}@)

| 参数 | 说明 |
| --- | --- |
| "pagedByParent" | |
| "SchemaCode" | |
| "childSchemaCode" | |
| "IsMobile" | |
| "isDesignMode" | |
| "filter" | |
| "userId" | |
| "listScopeType" | |
| "requireAssociatedBoHeaders" | |
| "ListViewSettingSortBy" | |
| "ListViewSettingSortDirection" | |
| "DataCount" | |
| "ReturnData" | |
| "WorkflowState" | |
| 返回值 |  |
| |  |


方法名称 : GetSchemaCodeRelatedObject(System.String,System.Boolean,System.Boolean,System.Boolean,System.Boolean,System.Boolean,System.Boolean,System.Boolean,System.Boolean,System.Boolean,System.Boolean,H3.DataModel.BizObjectSchema@,H3.DataModel.BizObjectSchemaSummary@,H3.DataModel.BizObjectSchema@,H3.DataModel.BizObjectSchemaSummary@,H3.SmartForm.ListViewSetting@,H3.SmartForm.ListViewSetting@,H3.SmartForm.FormSetting@,H3.SmartForm.FormSetting@,H3.App.FunctionNode@,H3.App.AppHeader@,H3.Workflow.Template.WorkflowTemplate@)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| "getSchema" | |
| "getSchemaSummary" | |
| "getDraftSchema" | |
| "getListviewSetting" | |
| "getDraftListviewSetting" | |
| "getFormsetting" | |
| "getDraftFormsetting" | |
| "getFunctionNode" | |
| "getAppHeader" | |
| "getWorkflowTemplate" | |
| "schema" | |
| "schemaSummary" | |
| "draftSchema" | |
| "draftSchemaSummary" | |
| "listviewSetting" | |
| "draftListviewSetting" | |
| "formSetting" | |
| "draftFormSetting" | |
| "functionNode" | |
| "appHeader" | |
| "workflowtemplate" | |
| 返回值 |  |
| |  |


方法名称 : GetBoForWeb(System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| "objectID" | |
| "userId" | |
| "userParentId" | |
| 返回值 |  |
| |  |


方法名称 : GetBosForWeb(System.String,System.String\[\],System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| "objectIds" | |
| "userId" | |
| "userParentId" | |
| 返回值 |  |
| |  |


方法名称 : GetBoEnableSheetHome(System.String,System.String,System.String,System.String,System.String@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| "objectId" | |
| "userId" | |
| "userParentId" | |
| "boName" | |
| "Message" | |
| 返回值 |  |
| |  |


方法名称 : PostTask(System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| "objectId" | |
| "userId" | |
| "title" | |
| "content" | |
| "remindType" | |
| "remindTime" | |
| "startTime" | |
| "currentUserId" | |
| "currentUserParentId" | |
| 返回值 |  |
| |  |


方法名称 : IsInstalledOK(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | |
| 返回值 |  |
| |  |


方法名称 : GetParentSchemaCodes(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| 返回值 |  |
| |  |


方法名称 : SubmitBizObject(System.String,H3.SmartForm.SmartFormPostComment,H3.Data.BoolValue,System.Boolean,System.Collections.Generic.List{H3.SmartForm.FileItem},System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.Int32,System.Boolean,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "actionName" | |
| "Comment" | |
| "approval" | |
| "ItemTypeIsApprove" | |
| "fileList" | |
| "ActivityCode" | |
| "InstanceId" | |
| "ParticipantId" | |
| "UnitId" | |
| "DepartmentName" | |
| "SchemaCode" | |
| "bizObjectObjectId" | |
| "bizObjectId" | |
| "Delegant" | |
| "TokenId" | |
| "workitemIsNotNull" | |
| "userid" | |
| 返回值 |  |
| |  |


方法名称 : GetPublishAppMenus(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | |
| 返回值 |  |
| |  |


方法名称 : GetSheetDisplayNames(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "sheetArray" | |
| 返回值 |  |
| |  |


方法名称 : LoadAssociatedSchemas

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetReportFilters(System.String,System.String,System.Collections.Generic.Dictionary{System.String,System.String}@)

| 参数 | 说明 |
| --- | --- |
| "reportCode" | |
| "reportId" | |
| "boolDic" | |
| 返回值 |  |
| |  |


方法名称 : ValidRequiredWhenSubmit(System.String,System.String,System.Int32,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "WorkitemId" | |
| "WorkflowCode" | |
| "WorkflowVersion" | |
| "InstanceId" | |
| "BizObjectId" | |
| "userId" | |
| "userParentId" | |
| 返回值 |  |
| |  |


方法名称 : CheckUnitValidate(System.String\[\],System.String,System.String,System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "unitCodes" | |
| "unitSelectionRange" | |
| "userId" | |
| "userParentId" | |
| "errorMessage" | |
| 返回值 |  |
| |  |


方法名称 : GetUserProperty(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "userIds" | |
| 返回值 |  |
| |  |


方法名称 : LoadTags

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : LoadUsers(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "unitId" | |
| "showUnActive" | |
| 返回值 |  |
| |  |


方法名称 : LoadOwnAndChildUnit(System.String,System.String,H3.Organization.UnitType)

| 参数 | 说明 |
| --- | --- |
| "unitIds" | |
| "userParentId" | |
| "unitType" | |
| 返回值 |  |
| |  |


方法名称 : LoadUnit(System.String)

| 参数 | 说明 |
| --- | --- |
| "unitId" | |
| 返回值 |  |
| |  |


方法名称 : LoadUnits(System.String)

| 参数 | 说明 |
| --- | --- |
| "unitId" | |
| 返回值 |  |
| |  |


方法名称 : SearchOrg(System.Int32,System.Int32,System.String,System.Boolean,System.Boolean,System.Boolean,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "fromNum" | |
| "toNum" | |
| "searchKey" | |
| "orgUnitVisible" | |
| "userVisible" | |
| "showUnActive" | |
| "unitSelectionRange" | |
| "userParentId" | |
| 返回值 |  |
| |  |


方法名称 : SearchRole(System.String)

| 参数 | 说明 |
| --- | --- |
| "keyWord" | |
| 返回值 |  |
| |  |


方法名称 : UpdateUserRoles(System.String,System.String\[\],System.String@)

| 参数 | 说明 |
| --- | --- |
| "userId" | |
| "RoleIds" | |
| "errorMessage" | |
| 返回值 |  |
| |  |


方法名称 : GetHomeListItem(System.Collections.Generic.Dictionary{System.String,System.Object},System.String,System.Int32@,System.Int32@,System.String@)

| 参数 | 说明 |
| --- | --- |
| "request" | |
| "userId" | |
| "total" | |
| "unFinished" | |
| "error" | |
| 返回值 |  |
| |  |


方法名称 : GetRoleUsersNameTable(System.String)

| 参数 | 说明 |
| --- | --- |
| "RoleId" | |
| 返回值 |  |
| |  |


方法名称 : UpdateScheduleRule(H3.Task.UserTaskRule,System.String@)

| 参数 | 说明 |
| --- | --- |
| "rule" | |
| "errorMsg" | 错误信息 |
| 返回值 |  |
| |  |


方法名称 : AddScheduleRule(H3.Task.UserTaskRule,System.String@)

| 参数 | 说明 |
| --- | --- |
| "rule" | |
| "errorMsg" | |
| 返回值 |  |
| |  |


方法名称 : LoadSchedules(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| 返回值 |  |
| |  |


方法名称 : SearchRoleUsers(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "keyWord" | 关键字 |
| "roleId" | 角色id |
| 返回值 |  |
| |  |


方法名称 : GetChildrenAcls(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "roleId" | |
| "AppCode" | |
| 返回值 |  |
| |  |


方法名称 : GetNodeSheetAndListViewActions(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "roleId" | 角色id |
| "code" | 应用编码 |
| 返回值 |  |
| |  |


方法名称 : SaveAclNode(System.String,System.String,H3.SmartForm.RoleAclNode,System.String@)

| 参数 | 说明 |
| --- | --- |
| "roleId" | 角色ID |
| "code" | 应用编码 |
| "node" | 权限节点 |
| "errorMsg" | 输出错误信息 |
| 返回值 |  |
| 错误代码 |  |


方法名称 : CopyRole(System.String,System.Int32,System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "roleName" | 角色名称 |
| "sortKey" | 排序值 |
| "sourceRoleId" | 源角色ID |
| "copyRoleId" | 复制后的角色ID |
| 返回值 |  |
| 错误代码 |  |


方法名称 : UpdateRoleUsers(System.String,System.String\[\],System.String@)

| 参数 | 说明 |
| --- | --- |
| "roleId" | 角色ID |
| "userIds" | 用户ID集合 |
| "errorMsg" | 错误信息 |
| 返回值 |  |
| 错误编码 |  |


方法名称 : GetUnitNameAndParentId(System.String)

| 参数 | 说明 |
| --- | --- |
| "unitId" | 组织Id或用户ID |
| 返回值 |  |
| 名称及parentid |  |


方法名称 : GetUnitNameTableForExport(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "unitids" | 组织机构Ids |
| 返回值 |  |
| |  |


方法名称 : GetUnitIdAndParentIdByNameOrByEmployeeNumber(System.String\[\],H3.Organization.UnitType)

| 参数 | 说明 |
| --- | --- |
| "unitNames" | 名称或工号集合 |
| "type" | 组织类型 |
| 返回值 |  |
| ID集合 |  |


方法名称 : GetUnitFullNameOrMobileAndIdTable(System.String\[\],System.Collections.Generic.List{System.String}@)

| 参数 | 说明 |
| --- | --- |
| "unitFullNameOrMobile" | 部门名称或手机号码 |
| "errorMessage" | 错误消息 |
| 返回值 |  |
| |  |


方法名称 : GetUnitIdAndFullNameOrMobile(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "ids" | |
| 返回值 |  |
| |  |


方法名称 : GetChildOuSummaries(System.String)

| 参数 | 说明 |
| --- | --- |
| "unitId" | 部门ID |
| 返回值 |  |
| 子节点 |  |


方法名称 : GetAllRoleSummaries

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetAllAppSolutions

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : RemoveTaskRule(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectId" | 提醒规则Id |
| 返回值 |  |
| |  |


方法名称 : GetPrintDingTalkApprelation(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用编码 |
| 返回值 |  |
| |  |


方法名称 : GetISVSolutionCodeByAppId(System.String)

| 参数 | 说明 |
| --- | --- |
| "dingAppId" | dingAppId |
| 返回值 |  |
| ISV套件对应的SolutionCode |  |


方法名称 : GetSuiteBySolutionCode(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | solution编码 |
| 返回值 |  |
| |  |


方法名称 : GetSuiteLogo(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | solution编码 |
| 返回值 |  |
| |  |


方法名称 : GetSuiteLogoUrl(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | solution编码 |
| 返回值 |  |
| |  |


方法名称 : ShareReport(System.Byte\[\],System.String,System.String,System.String,System.String,System.String,System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "bytes" | 图片 |
| "fileName" | 图片名 |
| "sender" | 发送者 |
| "cid" | 接收者 |
| "title" | 标题 |
| "text" | 描述 |
| "reportCode" | 报表编码 |
| "errorMsg" | 错误信息 |
| 返回值 |  |
| |  |


方法名称 : UpdateCorpSecret(System.String)

| 参数 | 说明 |
| --- | --- |
| "secret" | |
| 返回值 |  |
| |  |


方法名称 : GetCorpSecret

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetBehindCodesByAppCode(System.String,H3.SmartForm.SourceCodeType,System.Collections.Generic.Dictionary{System.String,System.String}@)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用编码 |
| "sourceCodeType" | 源码类型 |
| "javaScripts" | js代码 |
| 返回值 |  |
| |  |


方法名称 : GetAgileModifiedTime(System.String,H3.SmartForm.SourceCodeType)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用编码 |
| "sourceCodeType" | 源码类型 |
| 返回值 |  |
| |  |


方法名称 : SwitchContract(System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "on" | 开 |
| 返回值 |  |
| |
 |