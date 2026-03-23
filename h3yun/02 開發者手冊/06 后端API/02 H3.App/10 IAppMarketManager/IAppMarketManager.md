---
title: "IAppMarketManager"
source: "https://help.h3yun.com/contents/314/314.html"
category: "開發者手冊 / 后端API / H3.App / IAppMarketManager"
updated: 2025-12-18
tags:
  - h3yun
  - 開發者手冊
---
类名 : IAppMarketManager
说明 : 应用市场管理器，在这里实现与应用市场的交互，包括发布应用、安装应用等 
方法名称 : GetInstallableApps(H3.ServiceHub.AppMarketService.AgileAppCategory,System.String,System.Int32,System.Int32,System.Int32@,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "category" | 应用分类 |
| "keyword" | 应用关键字 |
| "pageIndex" | 分页索引 |
| "pageSize" | 分页大小 |
| "count" | 总数量 |
| "notShowSolutionApps" | 是否不显示解决方案应用 |
| 返回值 |  |
| 我可安装的应用 |  |


方法名称 : GetInstalledAppCount(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "engineCode" | 企业编码 |
| "notShowSolutionApps" | 是否不显示解决方案应用 |
| 返回值 |  |
| |  |


方法名称 : GetDirectionalApps

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetDirectionalApps(System.Int32,System.Int32,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "pageIndex" | 页码，从0开始 |
| "pageSize" | 页面项目数 |
| "recordCount" | 总条数 |
| 返回值 |  |
| |  |


方法名称 : GetDirectionalAppCount(System.String)

| 参数 | 说明 |
| --- | --- |
| "engineCode" | 企业编码 |
| 返回值 |  |
| |  |


方法名称 : Publish(System.String,H3.ServiceHub.AppMarketService.AgileAppCategory,System.String,System.Collections.Generic.List{System.Byte\[\]},System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 流程或应用的编码 |
| "category" | 分类 |
| "description" | 描述 |
| "screenshots" | 截图，最多5张 |
| "upgradLog" | 本次升级的升级描述 |
| 返回值 |  |
| 如果发布成功，则返回true，否则返回false |  |


方法名称 : PublishToEngine(System.String,H3.ServiceHub.AppMarketService.AgileAppCategory,System.String,System.Collections.Generic.List{System.Byte\[\]},System.String,System.String,System.String,System.String@)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 模板编码 |
| "category" | 分类 |
| "description" | 描述 |
| "screenShots" | 截图 |
| "upgradeLog" | 本次升级描述 |
| "targetEngineCode" | 目标引擎编码 |
| "message" | 留言信息 |
| "errorMessage" | 错误信息 |
| 返回值 |  |
| |  |


方法名称 : CheckAppSourceCodes(System.String,System.Boolean,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "appCode" | |
| "checkPublish" | |
| "checkDraft" | |
| 返回值 |  |
| |  |


方法名称 : Install(System.String\[\],System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "appCodes" | 安装的应用的编码 |
| "isDirectionalInstall" | 是否是安装定向应用 |
| 返回值 |  |
| 如果安装成功，则返回true，否则返回false |  |


方法名称 : InstallSolution(System.String,System.String\[\],System.String\[\]@)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | 解决方案编码 |
| "installAppCodes" | 需要安装的应用编码 |
| "appCodes" | 实际安装的应用编码 |
| 返回值 |  |
| 错误码 |  |


方法名称 : Uninstall(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 要卸载的应用的编码 |
| 返回值 |  |
| 如果卸载成功，则返回true，否则返回false |  |


方法名称 : GetAppContent(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用的编码 |
| 返回值 |  |
| 应用的内容 |  |


方法名称 : GetInstalledApps(System.Int32,System.Int32,System.Int32@,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "pageIndex" | 页码 |
| "pageSize" | 页大小 |
| "count" | 我安装的应用的数量的总数 |
| "notShowSolutionApps" | 是否不显示解决方案应用 |
| 返回值 |  |
| 我安装的应用 |  |


方法名称 : GetInstalledAppsByCode(System.String\[\],System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "appCodes" | 应用的列表 |
| "notShowSolutionApps" | 是否不显示解决方案应用 |
| 返回值 |  |
| 这款应用的安装情况，主要是安装版本之类的信息 |  |


方法名称 : GetMyDevelopedApps(H3.ServiceHub.AppMarketService.AgileAppState,System.Int32,System.Int32,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "state" | 要获得的应用的状态 |
| "pageIndex" | 分页的页码，从0开始计数 |
| "pageSize" | 分页的大小 |
| "count" | 总应用数量 |
| 返回值 |  |
| 我开发的所有应用 |  |


方法名称 : GetApp(System.String,H3.ServiceHub.AppMarketService.AgileAppCategory@,System.String@,System.String\[\]@,System.Collections.Generic.List{System.Byte\[\]}@)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用编码 |
| "category" | 应用的分类 |
| "description" | 应用的描述 |
| "upgradeLogs" | 应用的升级日志 |
| "screenshots" | 应用的升级日志 |
| 返回值 |  |
| 如果该应用不存在或者不是本企业发布的，则返回false，否则返回true |  |


方法名称 : GetSolutionAppCodes(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | |
| 返回值 |  |
| |  |


方法名称 : DeleteDirectionalApp(System.String)

| 参数 | 说明 |
| --- | --- |
| "appCode" | 应用编码 |
| 返回值 |  |
| |  |


方法名称 : GetAppCategoryByCode(System.String)

| 参数 | 说明 |
| --- | --- |
| "solutionCode" | 解决方案编码 |
| 返回值 |  |
| 返回解决方案 |  |


方法名称 : CreateSmartApp(System.String,System.String,H3.Entry.EntryOpenType,System.String@)

| 参数 | 说明 |
| --- | --- |
| "image" | 图片 |
| "code" | 应用编码 |
| "appRankType" | 解决方案编码 |
| "errorMsg" | 错误信息 |
| 返回值 |  |
| |  |


方法名称 : SyncChange(H3.Clusterware.EntryAppListenerMessage)

| 参数 | 说明 |
| --- | --- |
| "message" | |
| 返回值 |  |