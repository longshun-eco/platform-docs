---
title: "openDocument"
source: "https://open.dingtalk.com/document/development/jsapi-open-document"
category: "客户端JSAPI / 基础API / 文件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-open-document_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-open-document_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

在新页面打开文档。

调用dd.openDocument，在新页面打开文档。安卓端仅支持端内打开预览 pdf 格式文件，其他文件格式不支持端内访问。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.0.10 | 7.0.10 | 7.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11464) |
| 小程序 | 6.5.60 | 6.5.60 | 7.0.0 | 6.5.60 | 6.5.60 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11464) |

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
| filePath | String | 是 | 本地路径 | 文件路径（仅支持本地路径） |
| fileType | String | 否 | doc | 文件类型，已支持类型：   * doc * docx * xls * xlsx * ppt * pptx * pdf * zip |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **错误码**

| **错误码** | **描述** |
| --- | --- |
| 3 | 系统异常 |
| 2 | 参数无效 |

## **示例****代码**

### 默认出入参

```
dd.openDocument({
  filePath: '本地路径',
  fileType: 'doc',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```