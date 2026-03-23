---
title: "CustomSetting"
source: "https://help.h3yun.com/contents/510/359.html"
category: "開發者手冊 / 后端API / H3.Settings / CustomSetting"
updated: 2025-12-24
tags:
  - h3yun
  - 開發者手冊
---
类名 : CustomSetting
说明 : 自定义设置类 属性 : 

| 名称 | 说明 |
| --- | --- |
| SettingName | 设置名称 |
| SettingValue | 设置值 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_SettingName | 属性名称 |
| PropertyName\_SettingValue | 属性名称 |
| Setting\_Initialized | 是否初始化完成 |
| Setting\_AgencyMode | 委托采用的模式，0表示采用不真实转移任务的模式，1/Null/""表示真实将任务发送给代理人的模式 |
| Setting\_AgencyIdentityType | 委托的时候，被委托人操作的时候是用自己的身份还是使用委托人的身份 |
| Setting\_ExceptionManager | 异常管理员 |
| Setting\_DingTalkCorpId | DingTalk CorpID |
| Setting\_DingTalkCorpSecret | DingTalk Secret |
| Setting\_RegisteredOrgMessage | 是否注册了第三方平台组织机构变更消息 |
| Setting\_U8PlusCorpID | U8+ CorpID |
| Setting\_U8PlusCorpSecret | U8+ Secret |
| Setting\_LegacyAccessPointUrl | 属性名称 |
| Setting\_LegacyAccessPointLoginName | 属性名称 |
| Setting\_LegacyAccessPointPassword | 属性名称 |
| Setting\_LegacyAccessPointDomain | 属性名称 |
| Setting\_LastUpdateOldObjectBoostTime | 属性名称 |
| Setting\_LastRunOperationTime | 最后一次运行运营程序的时间 |
| Setting\_LastRunHierarchyTime | 最后一次运行层级关系的时间 |
| Setting\_OssEndPoint | oss终结点 |
| Setting\_OssThumbnailBucketName | oss 缩略图所属的bucket名称 |
| Setting\_H3Secret | 氚云Secret |
| Setting\_ManageContact | 管理第三方通讯录 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetValue\`\`1(H3.Settings.ISettingManager,System.String,\`\`0)

| 参数 | 说明 |
| --- | --- |
| "SettingName" | 设置管理器的接口 |
| "DefaultValue" | 设置的名称 |
| "SettingManager" | 默认值，如果设置的值为空，那么返回默认值 |
| 返回值 |  |
| 设置的值 |  |


方法名称 : GetAgencyIdentityType(H3.Settings.ISettingManager)

| 参数 | 说明 |
| --- | --- |
| "SettingManager" | 设置管理器，通过这个接口，我们可以获得全局性的设置信息，比如：显示的格式、流水号的格式等 |
| 返回值 |  |
| 委托的时候使用的身份模式 |  |


方法名称 : SetAgencyIdentityType(H3.Settings.ISettingManager,H3.Settings.AgencyIdentityType)

| 参数 | 说明 |
| --- | --- |
| "Type" | 设置管理器，通过这个接口，我们可以获得全局性的设置信息，比如：显示的格式、流水号的格式等 |
| "state" | 委托的时候使用的身份模式 |
| 返回值 |  |
| |  |


方法名称 : GetStateName(H3.Workflow.Instance.WorkflowInstanceState)

| 参数 | 说明 |
| --- | --- |
| "state" | 流程状态 |
| 返回值 |  |
| 流程状态的名称 |  |


方法名称 : GetStateName(H3.Workflow.Instance.WorkflowInstanceState,H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "approval" | 流程状态 |
| "state" | 流程的审批结果 |
| 返回值 |  |
| 流程状态名称 |  |


方法名称 : GetStateName(H3.Workflow.WorkItem.WorkItemState)

| 参数 | 说明 |
| --- | --- |
| "state" | 工作项的状态 |
| 返回值 |  |
| 工作项的名称 |  |


方法名称 : GetStateName(H3.Workflow.WorkItem.WorkItemState,H3.Data.BoolValue)

| 参数 | 说明 |
| --- | --- |
| "approval" | 工作项的状态 |
| "settingName" | 工作项是否审批通过 |
| 返回值 |  |
| 工作项状态的名称 |  |