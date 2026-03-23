---
title: "Query"
source: "https://help.h3yun.com/contents/533/369.html"
category: "開發者手冊 / 后端API / H3 / Query"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : Query
说明 : 查询数据库 
成员 : 

| 名称 | 说明 |
| --- | --- |
| ColumnName\_OriginateUnit | WorkflowInstance与WorkItem做联表查询的时候，两个表都存在OrgUnit列，这个列用于标示来自WorkflowInstance表的 |


构造方法名称 : #ctor(H3.Clusterware.EngineConfig,H3.Organization.IOrganization)

| 参数 | 说明 |
| --- | --- |
| "engineConfig" | |
| "organization" | |
| 返回值 |  |
| |  |


方法名称 : QueryTable(System.String,H3.Data.Database.Parameter\[\])

| 参数 | 说明 |
| --- | --- |
| "Sql" | 要执行的SQL语句 |
| "parameters" | 传入参数列表 |
| 返回值 |  |
| 返回查询结果集 |  |


方法名称 : BuildConditionGroupIn(System.String,System.String\[\],System.Collections.Generic.List{System.String},System.Collections.Generic.List{H3.Data.Database.Parameter})

| 参数 | 说明 |
| --- | --- |
| "ColumnName" | |
| "Values" | |
| "Conditions" | |
| "Parameters" | |
| 返回值 |  |
| |  |


方法名称 : GetObjectIds(System.Data.DataTable)

| 参数 | 说明 |
| --- | --- |
| "Table" | 传入的表 |
| 返回值 |  |
| 表中记录的ObjectId数组 |  |


方法名称 : Count(System.String,System.String\[\],H3.Data.Database.Parameter\[\])

| 参数 | 说明 |
| --- | --- |
| "TableName" | 表名称 |
| "Conditions" | 条件 |
| "parameters" | Sql参数 |
| 返回值 |  |
| 数量 |  |


方法名称 : QueryUrgency(System.String)

| 参数 | 说明 |
| --- | --- |
| "workItemId" | 不能为Null，否则返回一张空表 |
| 返回值 |  |
| 催办历史记录表 |  |


方法名称 : QueryUrgency(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "urger" | 催办人ID。不能为Null，否则返回空表。 |
| "instanceId" | 流程ID。不能为Null，否则返回空表。 |
| 返回值 |  |
| 催办历史记录表 |  |


方法名称 : BuildState(H3.Workflow.Instance.WorkflowInstanceState)

| 参数 | 说明 |
| --- | --- |
| "InstanceState" | 流程状态 |
| 返回值 |  |
| SQL语句中的条件 |  |


方法名称 : BuildState(H3.Workflow.WorkItem.WorkItemState)

| 参数 | 说明 |
| --- | --- |
| "State" | 工作项状态 |
| 返回值 |  |
| SQL条件 |  |


方法名称 : BuildWorkItemType(H3.Workflow.WorkItem.WorkItemType)

| 参数 | 说明 |
| --- | --- |
| "WorkItemType" | 工作项类型 |
| 返回值 |  |
| SQL条件语句 |  |


方法名称 : BuildWorkItemParticipant(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "Participant" | 参与者。不能为Null。 |
| "ParticipantIncludeDelegant" | 参与者是否包括委托人，如果为true，那么参与者不但要算WorkItem.Participant字段，还要算WorkItem.Delegant字段； |
| 返回值 |  |
| 参与者的匹配条件 |  |


方法名称 : GroupWorkItemSql(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "Conditions" | 条件 |
| 返回值 |  |
| 与流程表连接之后的SQL语句 |  |


方法名称 : GroupWorkItemSql(H3.Data.Database.DatabaseType,System.String\[\],System.Int32,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "DatabaseType" | 数据库类型 |
| "Conditions" | 条件 |
| "FromRowNum" | 起始行号，从1开始计数，包含起始行号 |
| "ToRowNum" | 结束行号，从1开始计数，不包含结束行号 |
| 返回值 |  |
| 与流程表连接之后的SQL语句 |  |


方法名称 : GroupWorkItemSql(H3.Data.Database.DatabaseType,System.String\[\],System.Int32,System.Int32,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "DatabaseType" | 数据库类型 |
| "Conditions" | 条件 |
| "FromRowNum" | 起始行号，从1开始计数，包含起始行号 |
| "ToRowNum" | 结束行号，从1开始计数，不包含结束行号 |
| "OrderBy" | 排序列 |
| "Ascending" | 是否升序 |
| 返回值 |  |
| 与流程表连接之后的SQL语句 |  |


方法名称 : GroupWorkItemCountSql(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "Conditions" | 条件 |
| 返回值 |  |
| 统计未完成流程的数量SQL |  |


方法名称 : QueryWorkItems(System.String,System.Int32,H3.Workflow.WorkItem.WorkItemType,H3.Workflow.WorkItem.WorkItemState,H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "InstanceId" | 流程ID。如果为Null，则忽略该条件 |
| "TokenId" | 步骤ID。如果为UnspecifiedID，则忽略该条件 |
| "WorkItemType" | 工作项类型。如果为Unspecified，则忽略该条件 |
| "State" | 工作项状态。如果为Unspecified，则忽略该条件 |
| "Approval" | 工作项的审批结果。如果为Unspecified，则忽略该条件 |
| 返回值 |  |
| 工作项ID |  |


方法名称 : QueryApprovedWorkItems(System.String,System.Int32,H3.Workflow.WorkItem.WorkItemType,H3.Workflow.WorkItem.WorkItemState)

| 参数 | 说明 |
| --- | --- |
| "InstanceId" | 流程ID。如果为Null，则忽略该条件 |
| "TokenId" | 步骤ID。如果为UnspecifiedID，则忽略该条件 |
| "WorkItemType" | 工作项类型。如果为Unspecified，则忽略该条件 |
| "State" | 工作项状态。如果为Unspecified，则忽略该条件 |
| 返回值 |  |
| 工作项ID |  |


方法名称 : QueryApproveWorkItems(System.String,System.Int32,System.Int32,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "userId" | |
| "from" | |
| "to" | |
| "appCodes" | |
| 返回值 |  |
| |  |


方法名称 : QueryWorkflowTrace(System.String,System.Int32,System.Int32,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "userId" | |
| "from" | |
| "to" | |
| "appCodes" | |
| 返回值 |  |
| |  |


方法名称 : QueryInstanceWorkItems(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "instances" | |
| 返回值 |  |
| |  |


方法名称 : QueryRejectedWorkItems(System.String,System.Int32,H3.Workflow.WorkItem.WorkItemType,H3.Workflow.WorkItem.WorkItemState)

| 参数 | 说明 |
| --- | --- |
| "InstanceId" | 流程ID。如果为Null，则忽略该条件 |
| "TokenId" | 步骤ID。如果为UnspecifiedID，则忽略该条件 |
| "WorkItemType" | 工作项类型。如果为Unspecified，则忽略该条件 |
| "State" | 工作项状态。如果为Unspecified，则忽略该条件 |
| 返回值 |  |
| 工作项ID |  |


方法名称 : QueryLastWorkItems(System.String,System.Int32,H3.Workflow.WorkItem.WorkItemType,H3.Workflow.WorkItem.WorkItemState)

| 参数 | 说明 |
| --- | --- |
| "InstanceId" | 流程ID。禁止为空 |
| "tokenId" | 步骤ID。如果为UnspecifiedID，则忽略该条件 |
| "ItemType" | 工作项类型。如果为Unspecified，则忽略该条件 |
| "State" | 工作项状态。如果为Unspecified，则忽略该条件 |
| 返回值 |  |
| 工作项ID |  |


方法名称 : QueryWorkItems(System.String\[\],System.String\[\],System.DateTime,System.DateTime,H3.Workflow.WorkItem.WorkItemState)

| 参数 | 说明 |
| --- | --- |
| "Instances" | 实例的ID，如果为UnspecifiedID，则忽略 |
| "Participants" | 接收者，如果为null，则忽略 |
| "From" | 最小接收时间，如果为System.DateTime.MinValue，则忽略 |
| "To" | 最大接收时间，如果为System.DateTime.MaxValue，则忽略 |
| "State" | 状态，如果为Unfinished，则查询出等待或者处理中的，如果为Unspecified，则忽略 |
| 返回值 |  |
| 工作项ID |  |


方法名称 : QueryWorkItemsAndTasks(System.String\[\],System.String,System.String\[\],System.DateTime,System.DateTime,System.Int32,System.Int32,H3.Workflow.WorkItem.WorkItemState,H3.Workflow.Instance.FilterType,System.Boolean,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "Originators" | |
| "Participant" | 参与人，默认当前用户 |
| "AppCodes" | |
| "From" | |
| "To" | |
| "FromRowNum" | |
| "ToRowNum" | |
| "State" | |
| "IsMyStart" | 0:待办,1:传阅,2:任务,3:全部 |
| "count" | |
| "Originators" | |
| 返回值 |  |
| |  |


方法名称 : QueryOriginatorWorkflowAndTasks(System.String\[\],System.String\[\],System.DateTime,System.DateTime,System.Int32,System.Int32,H3.Workflow.Instance.FilterType,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "AppCodes" | |
| "From" | |
| "To" | |
| "FromRowNum" | |
| "ToRowNum" | |
| "FilterType" | |
| "count" | |
| "Participant" | |
| 返回值 |  |
| |  |


方法名称 : CountWorkItemsAndTasks(System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "AppCodes" | |
| "participant" | |
| 返回值 |  |
| |  |


方法名称 : CountSolutionWorkItems(System.String,System.String\[\],H3.Workflow.WorkItem.WorkItemState)

| 参数 | 说明 |
| --- | --- |
| "appCodes" | |
| "state" | |
| "instances" | |
| 返回值 |  |
| |  |


方法名称 : QueryWorkItemDisplayAndParticipant(System.String\[\],H3.Workflow.WorkItem.WorkItemState)

| 参数 | 说明 |
| --- | --- |
| "state" | |
| "InstanceId" | |
| 返回值 |  |
| |  |


方法名称 : QueryParticipants(System.String,System.Int32,H3.Workflow.WorkItem.WorkItemType,H3.Workflow.WorkItem.WorkItemState)

| 参数 | 说明 |
| --- | --- |
| "TokenId" | 流程ID，不能为Null |
| "WorkItemType" | 步骤ID。如果为UnspecifiedID，则忽略该条件 |
| "State" | 工作项类型。如果为Unspecified，则忽略该条件 |
| "InstanceId" | 工作项状态。如果为Unspecified，则忽略该条件 |
| 返回值 |  |
| 参与者ID |  |


方法名称 : QueryParticipants(System.String,System.Int32,H3.Workflow.WorkItem.WorkItemType,System.String\[\],H3.Workflow.WorkItem.WorkItemState,H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "TokenId" | 流程ID。不能为Null |
| "WorkItemType" | 步骤ID。如果为UnspecifiedID，则忽略该条件 |
| "Participants" | 工作项类型。如果为Unspecified，则忽略该条件 |
| "State" | 参与者范围。如果为Null，则忽略该条件 |
| "Approval" | 工作项状态。如果为Unspecified，则忽略该条件 |
| "InstanceId" | 工作项审批结果。如果为Unspecified，则忽略该条件 |
| 返回值 |  |
| 参与者ID |  |


方法名称 : QueryLastParticipants(System.String)

| 参数 | 说明 |
| --- | --- |
| "BizObjectId" | |
| 返回值 |  |
| |  |


方法名称 : QueryParticipantsByBizObject(System.String)

| 参数 | 说明 |
| --- | --- |
| "originators" | 表单Id |
| 返回值 |  |
| 返回参与者 |  |


方法名称 : GetInstanceSheetNameFilters(System.String\[\],H3.Workflow.Instance.WorkflowInstanceState,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "instanceState" | 发起人 |
| "schemaCodes" | 流程状态 |
| "ParentInstanceId" | 编码 |
| 返回值 |  |
| |  |


方法名称 : QueryChildInstances(System.String,System.Int32,H3.Workflow.Instance.WorkflowInstanceState,H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "TokenId" | 流程ID。如果为Null，则忽略该条件 |
| "InstanceState" | 步骤ID。如果为Token.UnspecifiedID则忽略该条件 |
| "Approval" | 状态。如果为InstanceState.Unspecified，则忽略该条件 |
| "ParentInstanceId" | 审批结果。如果为Unspecified，则忽略该条件 |
| 返回值 |  |
| 子流程表 |  |


方法名称 : QueryChildInstance(System.String,System.Int32,H3.Workflow.Instance.WorkflowInstanceState,H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "TokenId" | 流程ID。如果为Null，则忽略该条件 |
| "InstanceState" | 步骤ID。如果为Token.UnspecifiedID则忽略该条件 |
| "Approval" | 状态。如果为InstanceState.Unspecified，则忽略该条件 |
| "ParentInstanceId" | 审批结果。如果为Unspecified，则忽略该条件 |
| 返回值 |  |
| 子流程表 |  |


方法名称 : QueryChildInstanceStates(System.String,System.Int32,H3.Workflow.Instance.WorkflowInstanceState,H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "TokenId" | |
| "InstanceState" | |
| "Approval" | |
| "conditions" | |
| 返回值 |  |
| |  |


方法名称 : QueryInstance(H3.Query.QueryConditionPara,System.Int32,System.Int32,System.String,System.Boolean,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "fromRow" | 条件 |
| "toRow" | 起始行号，包括本行 |
| "orderBy" | 结束行号，不包括本行 |
| "ascending" | 根据该列来进行排序 |
| "count" | 是否升序 |
| "Conditions" | 查询总数 |
| 返回值 |  |
| 流程表 |  |


方法名称 : CountInstance(H3.Query.QueryConditionPara)

| 参数 | 说明 |
| --- | --- |
| "Originators" | 条件，允许为Null |
| 返回值 |  |
| 记录的数量 |  |


方法名称 : GetQueryInstanceConditions(System.String\[\],System.String,H3.Workflow.Instance.WorkflowInstanceState,System.DateTime,System.DateTime)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 发起人条件，如果为Null，则表示忽略这个条件 |
| "InstanceState" | 流程模板名称编码，如果为Null，则表示忽略这个条件 |
| "CreatedTime\_From" | 流程实例状态条件，如果为Unspecified，则表示忽略这个条件 |
| "CreatedTime\_To" | 开始时间，如果为MinValue，则表示忽略这个条件 |
| "Originators" | 结束时间，如果为MaxValue，则表示忽略这个条件 |
| 返回值 |  |
| |  |


方法名称 : GetInstanceConditions(System.String\[\],System.String,System.String,H3.Workflow.Instance.WorkflowInstanceState,System.String,System.Int32,System.DateTime,System.DateTime,System.String,H3.Data.BoolValue,H3.Data.BoolValue,System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "OU" | 发起人。如果为Null，则忽略该条件 |
| "ParentInstanceID" | 发起人所属的机构，如果为Null，则忽略该条件 |
| "InstanceState" | 父流程ID，如果为Null，则忽略该条件 |
| "schemaCode" | 流程状态，如果为UnspecifiedID，则忽略该条件 |
| "WorkflowVersion" | 流程模板名称，如果为Null，则忽略该条件 |
| "CreatedTime\_From" | 流程模板版本号，如果为NullVersion，则忽略该条件 |
| "CreatedTime\_To" | 开始时间，如果为MinValue，则忽略该条件 |
| "InstanceName" | 结束时间，如果为MaxValue，则忽略该条件 |
| "Approval" | 流程实例的名称，流程实例的名称可以使通过流程模板定义出来的，也可以使由最终用户指定的，实际上，会优先用户指定的。如果该参数为空，则忽略该条件；否则，以LIKE %{InstanceName}%的形式进行匹配 |
| "Elapsed" | 审批结果，如果为Unspecified，则忽略该条件 |
| "RelatedUserId" | 是否超时，如果为Unspecified，则忽略该条件 |
| "schemaCodes" | 相关人ID,如果为Null,则忽略改条件 |
| "Originators" | 需要查的表单编码 |
| 返回值 |  |
| 查询流程实例表的条件 |  |


方法名称 : QueryInstance(System.String\[\],System.String,System.String,H3.Workflow.Instance.WorkflowInstanceState,System.String,System.Int32,System.DateTime,System.DateTime,System.String,H3.Data.BoolValue,H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "OU" | 发起人。如果为Null，则忽略该条件 |
| "ParentInstanceID" | 发起人所属的机构，如果为Null，则忽略该条件 |
| "InstanceState" | 父流程ID，如果为Null，则忽略该条件 |
| "schemaCode" | 流程状态，如果为UnspecifiedID，则忽略该条件 |
| "WorkflowVersion" | 流程模板名称，如果为Null，则忽略该条件 |
| "CreatedTime\_From" | 流程模板版本号，如果为NullVersion，则忽略该条件 |
| "CreatedTime\_To" | 开始时间，如果为MinValue，则忽略该条件 |
| "InstanceName" | 结束时间，如果为MaxValue，则忽略该条件 |
| "Approval" | 流程实例的名称，流程实例的名称可以使通过流程模板定义出来的，也可以使由最终用户指定的，实际上，会优先用户指定的。如果该参数为空，则忽略该条件；否则，以LIKE %{InstanceName}%的形式进行匹配 |
| "Elapsed" | 审批结果，如果为Unspecified，则忽略该条件 |
| "InstanceId" | 是否超时，如果为Unspecified，则忽略该条件 |
| 返回值 |  |
| 流程实例表 |  |


方法名称 : GetWorkItemByInstance(System.String)

| 参数 | 说明 |
| --- | --- |
| "InstanceId" | |
| 返回值 |  |
| |  |


方法名称 : GetWorkItemsByWorkflowInstanceId(System.String)

| 参数 | 说明 |
| --- | --- |
| "instanceId" | |
| 返回值 |  |
| |  |


方法名称 : GetInstanceTokens(System.String)

| 参数 | 说明 |
| --- | --- |
| "Participant" | |
| 返回值 |  |
| |  |


方法名称 : GetWorkItemConditions(System.String,System.DateTime,System.DateTime,H3.Workflow.WorkItem.WorkItemState,System.String,H3.Data.BoolValue,H3.Data.BoolValue,H3.Workflow.Instance.WorkflowInstanceState,System.String)

| 参数 | 说明 |
| --- | --- |
| "From" | 参与者，如果为Null，则忽略该条件 |
| "To" | 工作项接收的起始查询时间。如果为System.DateTime.MinValue则忽略该条件 |
| "State" | 工作项接收的结束查询时间。如果为System.DateTime.MaxValue则忽略该条件 |
| "InstanceName" | 工作项状态，如果为Unspecified，则忽略该条件 |
| "Approval" | 流程实例的名称，流程实例的名称可以使通过流程模板定义出来的，也可以使由最终用户指定的，实际上，会优先用户指定的。如果该参数为空，则忽略该条件；否则，以LIKE %{InstanceName}%的形式进行匹配 |
| "Elapsed" | 审批结果，如果为Unspecified，则表示忽略这个条件 |
| "InstanceState" | 是否已经超时，如果为Unspecified，则表示忽略这个条件 |
| "schemaCode" | 流程实例的状态，如果为Unspecified，则表示忽略这个条件 |
| "Participant" | 流程模板的编码，如果为空，则表示忽略这个条件 |
| 返回值 |  |
| 查询工作项的条件 |  |


方法名称 : GetWorkItemConditions(System.String,System.String,System.DateTime,System.DateTime,H3.Workflow.WorkItem.WorkItemState,System.String,H3.Data.BoolValue,H3.Data.BoolValue,H3.Workflow.Instance.WorkflowInstanceState,System.String)

| 参数 | 说明 |
| --- | --- |
| "TimeColumnName" | 参与者，如果为Null，则忽略该条件 |
| "From" | 时间字段名称 |
| "To" | 工作项接收的起始查询时间。如果为System.DateTime.MinValue则忽略该条件 |
| "State" | 工作项接收的结束查询时间。如果为System.DateTime.MaxValue则忽略该条件 |
| "InstanceName" | 工作项状态，如果为Unspecified，则忽略该条件 |
| "Approval" | 流程实例的名称，流程实例的名称可以使通过流程模板定义出来的，也可以使由最终用户指定的，实际上，会优先用户指定的。如果该参数为空，则忽略该条件；否则，以LIKE %{InstanceName}%的形式进行匹配 |
| "Elapsed" | 审批结果，如果为Unspecified，则表示忽略这个条件 |
| "InstanceState" | 是否已经超时，如果为Unspecified，则表示忽略这个条件 |
| "schemaCode" | 流程实例的状态，如果为Unspecified，则表示忽略这个条件 |
| "appId" | 流程模板的编码，如果为空，则表示忽略这个条件 |
| 返回值 |  |
| 查询工作项的条件 |  |


方法名称 : QueryWorkItem(System.String,System.String,System.Int32,System.String,System.String\[\],System.String\[\],System.DateTime,System.DateTime,H3.Workflow.WorkItem.WorkItemState,System.String,System.String,H3.Data.BoolValue,H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | 应用Id |
| "WorkflowVersion" | 流程模板编码，如果为Null，则忽略该条件 |
| "ActivityName" | 流程模板版本号，如果为NullVersion，则忽略该条件 |
| "Instances" | 活动名称，如果为Null，则忽略该条件 |
| "Participants" | 流程实例的范围，如果为Null，则忽略该条件 |
| "From" | 参与者的范围，如果为Null，则忽略该条件 |
| "To" | 工作项接收的起始查询时间。如果为System.DateTime.MinValue则忽略该条件 |
| "State" | 工作项接收的结束查询时间。如果为System.DateTime.MaxValue则忽略该条件 |
| "InstanceName" | 工作项的状态，如果为Unspecified，则忽略该条件 |
| "Receiptor" | 流程实例的名称，流程实例的名称可以使通过流程模板定义出来的，也可以使由最终用户指定的，实际上，会优先用户指定的。如果该参数为空，则忽略该条件；否则，以LIKE %{InstanceName}%的形式进行匹配 |
| "Approval" | 转移的接收人，如果为Null，则忽略该条件 |
| "Elapsed" | 审批结果，如果为Unspecified，则表示忽略这个条件 |
| "Participant" | 是否已经超时，如果为Unspecified，则表示忽略这个条件 |
| 返回值 |  |
| 工作项表 |  |


方法名称 : QueryWorkItem(System.String,H3.Workflow.WorkItem.WorkItemState,H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "State" | 工作项参与者，如果为空，则忽略该条件 |
| "Approval" | 工作项状态，如果为Unspecified，则忽略该条件 |
| "ConditionPara" | 工作项的审批结果，如果为Unspecified，则忽略该条件 |
| 返回值 |  |
| 工作项表 |  |


方法名称 : QueryWorkItem(H3.Query.QueryConditionPara,System.Int32,System.Int32,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "FromRowNum" | 查询工作项的条件 |
| "ToRowNum" | 起始行号，从1开始计数，包含起始行号 |
| "OrderBy" | 结束行号，从1开始计数，不包含结束行号 |
| "Ascending" | 排序列 |
| "participant" | 是否升序 |
| 返回值 |  |
| 工作项表 |  |


方法名称 : QueryWorkItem(System.String,System.String\[\],H3.Workflow.WorkItem.WorkItemState,System.Int32,System.Int32,System.String,System.Boolean,System.String\[\],System.DateTime,System.DateTime,System.DateTime,System.DateTime,System.Int32@,System.Data.DataTable@,System.Boolean,H3.Workflow.WorkItem.WorkItemType,System.String,H3.Workflow.WorkItem.WorkCriticalLevel,System.String,H3.Workflow.Instance.WorkflowInstanceState)

| 参数 | 说明 |
| --- | --- |
| "originators" | 参与者 |
| "state" | 发起人 |
| "fromRowNum" | 状态 |
| "toRowNum" | 起始行号，从1开始计数，包含起始行号 |
| "orderBy" | 结束行号，从1开始计数，包含结束行号 |
| "ascending" | 排序列 |
| "schemaCodes" | 是否升序 |
| "recieveFrom" | SchemacCodes |
| "recieveTo" | 接收的开始时间 |
| "finishFrom" | 接收的开始时间接收的结束时间 |
| "finishTo" | |
| "count" | |
| "commentTable" | 数量 |
| "groupbyInstanceId" | 工作项的评论表 |
| "workItemType" | |
| "searchKey" | 任务类型 |
| "criticalLevel" | 搜索关键字 |
| "schemaCode" | 紧要程度 |
| "instanceState" | 模式编码 |
| "participant" | 流程状态 |
| 返回值 |  |
| 工作项表 |  |


方法名称 : GetWorkItemSheetNameFilters(System.String,System.String\[\],H3.Workflow.WorkItem.WorkItemState,H3.Workflow.WorkItem.WorkItemType,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "originators" | 参与者 |
| "workItemState" | 发起人 |
| "workItemType" | 状态 |
| "schemaCodes" | 类别 |
| "Participant" | 编码 |
| 返回值 |  |
| |  |


方法名称 : CountWorkItems(System.String,System.String\[\],H3.Workflow.WorkItem.WorkItemState,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "Originators" | |
| "State" | |
| "schemaCodes" | |
| "UserID" | |
| 返回值 |  |
| |  |


方法名称 : QueryUnfinishedAndSnsCount(System.String,System.String\[\],System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "schemaCodes" | 用户id |
| "UnfinishedCount" | 表单编码 |
| "ConditionPara" | 返回为完成数量 |
| 返回值 |  |
| |  |


方法名称 : QueryWorkItem(H3.Query.QueryConditionPara,System.Int32,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "FromRowNum" | 查询工作项的条件 |
| "ToRowNum" | 起始行号，从1开始计数，包含起始行号 |
| "instanceId" | 结束行号，从1开始计数，不包含结束行号 |
| 返回值 |  |
| 工作项表 |  |


方法名称 : QueryWorkitem(System.String)

| 参数 | 说明 |
| --- | --- |
| "Originator" | |
| 返回值 |  |
| |  |


方法名称 : GetOriginatorConditionForMonitor(System.String)

| 参数 | 说明 |
| --- | --- |
| "Originators" | 如果为Null/""，那么返回Null，表示不需要匹配发起人的条件； 如果发起人无法找到，那么返回Originator=''这样的条件，在数据库中将匹配不到流程； 如果发起人是公司，那么返回Null，表示不需要匹配发起人的条件； 如果发起人是群，那么获得者群的成员，然后去根据各个成员的逻辑来搜索； 如果发起人是OU，那么就去匹配该OU及其子OU，返回WorkflowInstance.OrgUnit IN ('OU1', 'OU2'...)； 如果发起人是组，那么匹配WorkflowInstance.OriginatedGroup=Originator； 如果发起人是用户，那么匹配WorkflowInstance.Originator=Originator |
| 返回值 |  |
| |  |


方法名称 : GetOriginatorConditionForMonitor(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "Orgs" | 如果为Null/""，那么返回Null，表示不需要匹配发起人的条件； 如果发起人无法找到，那么返回Originator=''这样的条件，在数据库中将匹配不到流程； 如果发起人是公司，那么返回Null，表示不需要匹配发起人的条件； 如果发起人是群，那么获得者群的成员，然后去根据各个成员的逻辑来搜索； 如果发起人是OU，那么就去匹配该OU及其子OU，返回WorkflowInstance.OrgUnit IN ('OU1', 'OU2'...)； 如果发起人是组，那么匹配WorkflowInstance.OriginatedGroup=Originator； 如果发起人是用户，那么匹配WorkflowInstance.Originator=Originator |
| 返回值 |  |
| |  |


方法名称 : GetQueryWorkItemByOrgConditionForMonitor(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "PostTable" | 如果为Null/""，那么返回Null，表示不需要匹配参与人的条件； 如果发起人无法找到，那么返回Participant=''这样的条件，在数据库中将匹配不到工作项； 如果发起人是公司，那么返回Null，表示不需要匹配参与人的条件； 如果发起人是OU，那么就去匹配该OU及其子OU，返回WorkItem.OrgUnit IN ('OU1', 'OU2'...)； 如果发起人是组，那么匹配WorkItem.ParticipateGroup=AdminOrg； 如果发起人是用户，那么匹配WorkItem.Participant=AdminOrg |
| 返回值 |  |
| |  |


方法名称 : QuerySNSPostFile(System.Data.DataTable)

| 参数 | 说明 |
| --- | --- |
| "UserId" | |
| 返回值 |  |
| |  |


方法名称 : QuerySNSFeed(System.String,System.String\[\],System.DateTime,System.DateTime,System.String,System.Collections.Generic.List{System.String},System.Int32,System.Int32,System.Data.DataTable@,System.Data.DataTable@,System.Data.DataTable@,H3.SNS.SNSPostFileHeader\[\]@,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "FromRow" | 用户ID |
| "ToRow" | 新闻分页的起始行号 |
| "FeedTable" | 新闻分页的结束行号 |
| "CommentTable" | 返回的新闻信息表 |
| "Sender" | 返回的新闻相关的评论信息表 |
| "FromDate" | 发送人 |
| "ToDate" | 时间段 |
| "appCode" | 时间段 |
| "PostTable" | 应用编码 |
| "PostFileHeaders" | 提交数据信息 |
| "Total" | 附件信息 |
| "SchemaCodes" | 总数 |
| "UserId" | 子模块 |
| 返回值 |  |
| |  |


方法名称 : QuerySNSFeed(System.String,System.String,System.Data.DataTable@,System.Data.DataTable@,System.Data.DataTable@,H3.SNS.SNSPostFileHeader\[\]@,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "LastTime" | 用户id |
| "FeedTable" | 最后获取时间 |
| "CommentTable" | 返回消息数据 |
| "PostTable" | 返回评论数据 |
| "PostFileHeaders" | 返回发表数据 |
| "UnfinishedCount" | 附件信息 |
| "UserId" | 未读条数 |
| 返回值 |  |
| |  |


方法名称 : QuerySNSPostFeed(System.String,System.String,System.Data.DataTable@,System.Data.DataTable@,System.Data.DataTable@,H3.SNS.SNSPostFileHeader\[\]@)

| 参数 | 说明 |
| --- | --- |
| "TargetId" | 用户Id |
| "FeedTable" | 目标Id |
| "CommentTable" | 返回动态信息 |
| "PostTable" | 评论信息 |
| "PostFileHeaders" | |
| "UserId" | |
| 返回值 |  |
| |  |


方法名称 : QuerySnsPostFeedById(System.String,System.String,System.Data.DataTable@,System.Data.DataTable@,System.Data.DataTable@,H3.SNS.SNSPostFileHeader\[\]@)

| 参数 | 说明 |
| --- | --- |
| "ObjectId" | |
| "FeedTable" | |
| "CommentTable" | |
| "PostTable" | |
| "PostFileHeaders" | |
| "BizObjectId" | |
| 返回值 |  |
| |  |


方法名称 : CountSNSPostByBizObjectId(System.String)

| 参数 | 说明 |
| --- | --- |
| "bizObjectId" | |
| 返回值 |  |
| |  |


方法名称 : QuerySNSPostByBizObjectId(System.String,System.Int32,System.Int32,System.Data.DataTable@,System.Data.DataTable@,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "fromRow" | |
| "toRow" | |
| "PostTable" | |
| "PostFileHeaderTable" | |
| "count" | |
| "BizObjectId" | |
| 返回值 |  |
| |  |


方法名称 : QuerySNSPostByBizObject(System.String,System.Data.DataTable@,System.Data.DataTable@,System.Data.DataTable@)

| 参数 | 说明 |
| --- | --- |
| "PostTable" | boId |
| "PostFileHeaderTable" | 返回信息 |
| "CommentTable" | 附件信息 |
| "ObjectId" | 评论信息 |
| 返回值 |  |
| |  |


方法名称 : QuerySnsPostById(System.String,System.Data.DataTable@,System.Data.DataTable@,System.Data.DataTable@)

| 参数 | 说明 |
| --- | --- |
| "PostTable" | |
| "PostFileHeaderTable" | |
| "CommentTable" | |
| "TargetId" | |
| 返回值 |  |
| |  |


方法名称 : QuerySNSLike(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "UserId" | |
| "TargetId" | |
| 返回值 |  |
| |  |


方法名称 : QueryTaskByTarget(System.String)

| 参数 | 说明 |
| --- | --- |
| "targetId" | TargetId |
| 返回值 |  |
| |  |


方法名称 : QueryTaskCountByTarget(System.String)

| 参数 | 说明 |
| --- | --- |
| "TaskId" | |
| 返回值 |  |
| |  |


方法名称 : QueryTaskByTaskId(System.String)

| 参数 | 说明 |
| --- | --- |
| "UserId" | |
| 返回值 |  |
| |  |


方法名称 : QueryTask(System.String,System.String\[\],System.String\[\],H3.Task.TaskState,System.DateTime,System.DateTime,System.Int32@,System.Int32,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "Senders" | |
| "SchemaCodes" | |
| "State" | |
| "FromRowNum" | |
| "FromDate" | |
| "ToDate" | |
| "Total" | |
| "EndRowNum" | |
| "UserId" | |
| 返回值 |  |
| |  |


方法名称 : CountTasks(System.String,System.String\[\],System.String\[\],H3.Task.TaskState)

| 参数 | 说明 |
| --- | --- |
| "Senders" | |
| "SchemaCodes" | |
| "State" | |
| "UserId" | |
| 返回值 |  |
| |  |


方法名称 : QueryTask(System.String,System.String,System.String\[\],System.Int32@,System.Int32,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "Sender" | |
| "SchemaCodes" | |
| "Total" | |
| "FromRowNum" | |
| "EndRowNum" | |
| "userId" | |
| 返回值 |  |
| |  |


方法名称 : QueryUnifinishedTaskCount(System.String,System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "sender" | 接收者 |
| "schemaCodes" | 发送者 |
| "schemaCode" | |
| 返回值 |  |
| |  |


方法名称 : QueryTotalUserCount

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : UpgradeBizObjectIconId(System.String,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "propertyName" | 对象编码 |
| "isChange" | 属性名称 |
| "SettingManager" | 是否变更现有IconId的值 |
| 返回值 |  |
| |
 |