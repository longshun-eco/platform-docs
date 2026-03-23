---
title: "FileHeader"
source: "https://help.h3yun.com/contents/450/661.html"
category: "開發者手冊 / 后端API / H3.Data / FileHeader"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : FileHeader
说明 : 附件头信息，主要记录附件的摘要信息 属性 : 

| 名称 | 说明 |
| --- | --- |
| FileId | 附件对象的Id |
| CreatedBy | 用户ID |
| ModifiedBy | 最后一次变更的用户的Id |
| ContentType | 获取或设置附件的类型 |
| IsImage | 是否是图片类型的 |
| ContentLength | 获取或设置附件字节大小 |
| FileName | 文件的名称 |
| Description | 文件的描述信息 |
| CreatedTime | 文件的创建时间 |
| ModifiedTime | 最后一次修改时间 |
| FileFlag | 文件的标识位 |
| SortKey | 上传顺序 |
| Printable | 是否可以被打印 |
| Downloadable | 是否可以被下载 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName\_CreatedBy | 属性名称 |
| PropertyName\_ModifiedBy | 属性名称 |
| PropertyName\_ContentType | 附件的类型 |
| PropertyName\_ContentLength | 附件字节大小 |
| PropertyName\_FileName | 属性名称 |
| PropertyName\_Description | 属性名称 |
| PropertyName\_CreatedTime | 属性名称 |
| PropertyName\_ModifiedTime | 属性名称 |
| DefaultFileFlag | 默认的标志位 |
| PropertyName\_FileFlag | 属性名称 |
| PropertyName\_SortKey | 上传顺序值 |
| FileFlag\_DisableDownload | 禁用下载 |
| FileFlag\_DisablePrint | 禁用打印 |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : IsImageType(System.String)

| 参数 | 说明 |
| --- | --- |
| "contentType" | 附件的content type |
| 返回值 |  |
| 如果是图片类型，则返回true，否则返回false |  |


方法名称 : GetThumbnailUrl(System.String,System.String,System.String,System.String,H3.Data.FileServiceType)

| 参数 | 说明 |
| --- | --- |
| "ossEndPoint" | oss地址 |
| "bucketName" | bucket name |
| "engineCode" | 引擎编码 |
| "fileId" | 文件Id |
| "type" | 存储服务的类型 |
| 返回值 |  |
| https格式的缩略图地址 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | |
| 返回值 |  |
| |  |