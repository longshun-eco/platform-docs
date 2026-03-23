---
title: "FileSystemManager.saveFile"
source: "https://open.dingtalk.com/document/development/jsapi-file-system-manager-save-file"
category: "客户端JSAPI / 文件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-file-system-manager-save-file_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-file-system-manager-save-file_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用FileSystemManager.saveFile，将本地临时文件保存为本地缓存文件或本地用户文件。

> 本接口会移动临时文件，因此调用成功后，本地临时路径的tempFilePath将不可用。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.5.26 | 6.5.26 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10275) |

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
| tempFilePath | String | 是 | 本地临时文件路径示例值 | 本地临时文件路径。 |
| filePath | String | 否 | ${dd.env.USER\_DATA\_PATH}/newDir/img.png | 指定该参数存储为本地用户文件时，该参数需要指定存储后文件的名称和后缀。  例如${dd.env.USER\_DATA\_PATH}/newDir/img.png。 filePath指定的目录如果不存在，该接口会按照指定的路径创建目录并保存文件。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| savedFilePath | String | filePath示例值 | 文件保存的路径。 |

## **错误码**

| **错误码** | **描述** |
| --- | --- |
| 10022 | filePath指定的文件路径错误。 |
| 3 | 文件读取未知错误。 |

## **示例****代码**

### 默认出入参

```javascript
const fileSystemManager = dd.getFileSystemManager();

fileSystemManager.saveFile({
  filePath: '${dd.env.USER_DATA_PATH}/newDir/img.png',
  tempFilePath: '**',
  success: (res) => {
    const { savedFilePath } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "savedFilePath": "***" }
```