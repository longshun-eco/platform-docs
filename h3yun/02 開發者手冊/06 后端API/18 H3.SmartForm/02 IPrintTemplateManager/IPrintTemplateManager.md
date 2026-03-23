---
title: "IPrintTemplateManager"
source: "https://help.h3yun.com/contents/562/465.html"
category: "開發者手冊 / 后端API / H3.SmartForm / IPrintTemplateManager"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : IPrintTemplateManager
说明 : 套打接口 
方法名称 : GetDraftPrintTemplateHeaders(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| 返回值 |  |
| |  |


方法名称 : GetPublishPrintTemplateHeaders(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| 返回值 |  |
| |  |


方法名称 : GetDraftPrintTemplate(System.String)

| 参数 | 说明 |
| --- | --- |
| "printTemplateCode" | |
| 返回值 |  |
| |  |


方法名称 : GetPublishPrintTemplate(System.String)

| 参数 | 说明 |
| --- | --- |
| "printTemplateCode" | |
| 返回值 |  |
| |  |


方法名称 : AddPrintTemplate(System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| "printTemplateCode" | |
| "name" | |
| 返回值 |  |
| |  |


方法名称 : RemovePrintTemplateByObjectID(System.String)

| 参数 | 说明 |
| --- | --- |
| "printTemplateCode" | |
| 返回值 |  |
| |  |


方法名称 : RemovePrintTemplateBySchemaCode(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| 返回值 |  |
| |  |


方法名称 : UpdateDraftPrintTemplate(H3.Printing.PrintTemplateWrapper)

| 参数 | 说明 |
| --- | --- |
| "wrapper" | |
| 返回值 |  |
| |  |


方法名称 : UpdateDraftPrintTemplateDisplayName(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "printTemplateCode" | |
| "newname" | |
| 返回值 |  |
| |  |


方法名称 : PublishPrintTemplate(System.String)

| 参数 | 说明 |
| --- | --- |
| "printTemplateCode" | |
| 返回值 |  |
| |  |


方法名称 : AddOrUpdatePrintTemplateImage(System.String,System.String,System.String,System.String,System.Byte\[\])

| 参数 | 说明 |
| --- | --- |
| "engineCode" | |
| "schemaCode" | |
| "pritemplateCode" | |
| "field" | |
| "content" | |
| 返回值 |  |
| |  |


方法名称 : RemovePrintTemplateImage(System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "engineCode" | |
| "schemaCode" | |
| "pritemplateCode" | |
| "field" | |
| 返回值 |  |
| |  |


方法名称 : GetPrintTemplateImage(System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "engineCode" | |
| "schemaCode" | |
| "pritemplateCode" | |
| "field" | |
| 返回值 |  |
| |
 |