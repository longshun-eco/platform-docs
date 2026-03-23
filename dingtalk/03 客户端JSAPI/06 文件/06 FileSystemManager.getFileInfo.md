---
title: "FileSystemManager.getFileInfo"
source: "https://open.dingtalk.com/document/development/jsapi-file-system-manager-get-file-info"
category: "客户端JSAPI / 文件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-file-system-manager-get-file-info_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-file-system-manager-get-file-info_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用FileSystemManager.getFileInfo，获取本地临时文件、本地缓存文件和本地用户文件的信息。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.5.26 | 6.5.26 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10267) |

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
| filePath | String | 是 | ${dd.env.USER\_DATA\_PATH}/test.txt | 文件的路径。 本地临时文件路径，可调用选择图片或选择视频获取。 本地缓存文件和本地用户文件路径，可调用保存文件获取。 |
| digestAlgorithm | String | 否 | \*\*\* | 文件编码，默认md5。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| size | Number | 100 | 文件大小，单位Byte。 |
| digest | String | 2421fcb1263b9530df88f7f002e78ea5 | 文件md5加密后的信息。 |

## **示例****代码**

### 默认出入参

```javascript
const fileSystemManager = dd.FileSystemManager();

fileSystemManager.getFileInfo({
  filePath: '`${dd.env.USER_DATA_PATH}/test.txt`',
  digestAlgorithm: '***',
  success: (res) => {
    const { size, digest } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "size": 1, "digest": "2421fcb1263b9530df88f7f002e78ea5" }
```