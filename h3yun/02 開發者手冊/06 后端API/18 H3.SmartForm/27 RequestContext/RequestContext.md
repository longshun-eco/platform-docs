---
title: "RequestContext"
source: "https://help.h3yun.com/contents/587/621.html"
category: "開發者手冊 / 后端API / H3.SmartForm / RequestContext"
updated: 2025-12-18
tags:
  - h3yun
  - 開發者手冊
---
类名 : RequestContext
说明 : 请求的上下文 属性 : 

| 名称 | 说明 |
| --- | --- |
| ValueTable | 请求上下文的各个变量的值 |
| Item(System.String) | 根据变量的名称获得变量的值 |
| UserHostAddress | 用户的地址 |
| BrowserPlatform | 用户使用的浏览器的平台 |
| Browser | 用户使用的浏览器 |
| IsMobile | 用户的客户端是否是移动设备 |
| UserContext | 获得当前登陆用户 |
| ErrorMessage | 错误信息 |
| Engine | 获取当前引擎实例对象 |
| CacheTimeStamp | 时间戳 |



构造方法名称 : #ctor(H3.Web.UserContext,System.Collections.Generic.Dictionary{System.String,System.String},H3.IEngine)

| 参数 | 说明 |
| --- | --- |
| "user" | 当前用户 |
| "valueTable" | 请求上下文的各个变量的值 |
| "engine" | 引擎实例对象 |
| 返回值 |  |
| |  |


方法名称 : GetValue\`\`1(System.String,\`\`0)

| 参数 | 说明 |
| --- | --- |
| "name" | 变量的名称 |
| "defaultValue" | 如果变量不存在或者无法转换，则返回该默认值 |
| 返回值 |  |
| 变量的值 |  |


方法名称 : GetObjectTrack(System.String)

| 参数 | 说明 |
| --- | --- |
| "objectName" | 对象名称 |
| 返回值 |  |
| 键值对 |  |