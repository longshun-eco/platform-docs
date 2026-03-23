---
title: "isLocalFileExist"
source: "https://open.dingtalk.com/document/development/jsapi-is-local-file-exist"
category: "客户端JSAPI / 基础API / 文件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-is-local-file-exist_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-is-local-file-exist_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用isLocalFileExist，批量检测本地文件是否存在。

PC端使用downLoadFile接口下载后的URL在本地是否存在来判断。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11664) |
| 小程序 | 不支持 | 不支持 | 不支持 | 不支持 | - |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| url | String | 是 | http://static.dingtalk.com/media/lADOADTWJM0C2M0C7A\_748\_728.jpg\_60x60q90.jpg | url是缓存文件的key。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
|  | Array<Object> |  |  |

## **示例****代码**

### 默认出入参

```javascript
const res = dd.isLocalFileExist({
  url: 'http://static.dingtalk.com/media/lADOADTWJM0C2M0C7A_748_728.jpg_60x60q90.jpg',
});
console.log(res);
// res: [{url: 'url示例值',path: 'path示例值',isExist: true,}]
```

返回对象示例：

```json
[{ "url": "url示例值", "path": "path示例值", "isExist": true }]
```