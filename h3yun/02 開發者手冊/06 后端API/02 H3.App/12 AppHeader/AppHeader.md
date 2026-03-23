---
title: "AppHeader"
source: "https://help.h3yun.com/contents/316/317.html"
category: "開發者手冊 / 后端API / H3.App / AppHeader"
updated: 2025-12-18
tags:
  - h3yun
  - 開發者手冊
---
类名 : AppHeader
说明 : 应用头信息，用来记录应用的名称、菜单类型等应用级的信息 属性 : 

| 名称 | 说明 |
| --- | --- |
| Code | 节点编码(类型内唯一) |
| DisplayName | 显示名称 |
| IconCss | 获取或设置图标的CSS名称 |
| AppSource | 应用市场中应用的源类型，自定义类型/安装的SaaS |
| IsDirectionalInstalled | 标记应用是否是定向安装的 主要是用于非开发者安装定向应用后限制其再次定向发布 因为定向应用安装后AppSource都改成了Custom，已经无法用于判断是否是自建应用 |
| DefaultMenus | 默认菜单 |
| ReportPageAndReportWidgetIds | 报表页Code，首页显示报表 |
| MobileSortType | 移动端排序类型(ERROR:该属性不是特别明确) |
| Solution | 所属解决方案 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_Code | 属性名称 |
| PropertyName\_DisplayName | 属性名称 |
| PropertyName\_IconCss | 图标CSS名称 |
| PropertyName\_AppSource | 属性名称 |
| PropertyName\_IsDirectionalInstalled | 属性名称 |
| PropertyName\_DefaultMenus | 属性名称 |
| PropertyName\_ReportPageAndReportWidgetIds | 属性名称 |
| PropertyName\_MobileSortType | 移动端排序类型(ERROR:该属性不是特别明确) |
| PropertyName\_Solution | 所属解决方案 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : GetKeyNames

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 键值名称数组 |  |


方法名称 : GetKeyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "KeyName" | 键的名称 |
| 返回值 |  |
| 键的值 |  |


方法名称 : ToString

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 返回应用头部字符串 |  |