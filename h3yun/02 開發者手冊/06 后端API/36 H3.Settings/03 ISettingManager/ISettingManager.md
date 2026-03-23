---
title: "ISettingManager"
source: "https://help.h3yun.com/contents/511/362.html"
category: "開發者手冊 / 后端API / H3.Settings / ISettingManager"
updated: 2025-12-16
tags:
  - h3yun
  - 開發者手冊
---
类名 : ISettingManager
说明 : 设置管理器，通过这个接口，我们可以获得全局性的设置信息，比如：显示的格式、流水号的格式等 
方法名称 : GetCustomSetting(System.String)

| 参数 | 说明 |
| --- | --- |
| "settingName" | 设置的名称 |
| 返回值 |  |
| 设置的值 |  |


方法名称 : SetCustomSetting(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "settingValue" | 设置的名称 |
| | 设置的值 |
| 返回值 |  |
| 如果设置成功，则返回true，否则返回false |  |


方法名称 : GetWebSettings

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 跟Portal相关的设置 |  |