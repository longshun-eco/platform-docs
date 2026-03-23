---
title: "IBizObjectTrackManager"
source: "https://help.h3yun.com/contents/378/408.html"
category: "開發者手冊 / 后端API / H3.DataModel / IBizObjectTrackManager"
updated: 2025-12-13
tags:
  - h3yun
  - 開發者手冊
---
类名 : IBizObjectTrackManager
说明 : 数据痕迹管理器 
方法名称 : Add(H3.DataModel.BizObjectPropertyTrack\[\])

| 参数 | 说明 |
| --- | --- |
| "tracks" | 要记录的痕迹 |
| 返回值 |  |
| |  |


方法名称 : QueryTable(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "bizObjectId" | 业务对象的ID |
| "propertyName" | 项名称 |
| 返回值 |  |
| 痕迹表，里面会包含修改时间、修改人、活动名称和修改后的值等信息 |  |


方法名称 : Query(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "bizObjectId" | 业务对象的ID |
| "propertyName" | 项名称 |
| 返回值 |  |
| 痕迹记录的ID |  |


方法名称 : GetTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "trackId" | 痕迹记录的ID |
| 返回值 |  |
| 痕迹记录 |  |


方法名称 : RemoveBizObject(System.String)

| 参数 | 说明 |
| --- | --- |
| "bizObjectId" | 业务对象的ID |
| 返回值 |  |
| |  |