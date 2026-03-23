---
title: "ViewSetting"
source: "https://help.h3yun.com/contents/617/804.html"
category: "開發者手冊 / 后端API / H3.SmartForm / ViewSetting"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : ViewSetting
说明 : 视图设置 属性 : 

| 名称 | 说明 |
| --- | --- |
| SchemaCode | 获取或设置流程模板包编码 |
| ModifiedTime | 最近一次修改时间 |
| Javascript | 获取或设置表单嵌入的Javascript |
| BehindCode | controller代码 |
| Actions | 获取或设置功能动作 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName\_SchemaCode | 编码属性名称 |
| \_SchemaCode | 流程模板包编码 |
| PropertyName\_ModifiedTime | 编码属性名称 |
| PropertyName\_Javascript | 表单嵌入的Javascript |
| PropertyName\_BehindCode | controller代码属性 |
| \_BehindCode | controller代码 |
| PropertyName\_Actions | 功能动作 |
| \_Actions | 视图操作集合 |


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
| |  |


方法名称 : GetKeyValue(System.String)

| 参数 | 说明 |
| --- | --- |
| "KeyName" | |
| 返回值 |  |
| |  |


方法名称 : ReadXml(System.Xml.XmlReader)

| 参数 | 说明 |
| --- | --- |
| "reader" | |
| 返回值 |  |
| |  |


方法名称 : WriteXml(System.Xml.XmlWriter)

| 参数 | 说明 |
| --- | --- |
| "writer" | |
| 返回值 |  |
| |  |