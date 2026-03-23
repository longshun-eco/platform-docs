---
title: "FileSystemManager.unzip"
source: "https://open.dingtalk.com/document/development/jsapi-file-system-manager-unzip"
category: "客户端JSAPI / 文件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-file-system-manager-unzip_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-file-system-manager-unzip_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用FileSystemManager.unzip，解压本地用户文件。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.5.26 | 6.5.26 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10278) |

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
| targetPath | String | 是 | ${dd.env.USER\_DATA\_PATH}/test | 解压后存放文件的目录。 |
| zipFilePath | String | 是 | ${dd.env.USER\_DATA\_PATH}/test.zip | 压缩文件的路径，只允许是zip压缩文件。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| success | Boolean | true | 解压成功时，返回true。 |

## **示例****代码**

### 默认出入参

```javascript
const fileSystemManager = dd.FileSystemManager();

fileSystemManager.unzip({
  targetPath: '${dd.env.USER_DATA_PATH}/test',
  zipFilePath: '${dd.env.USER_DATA_PATH}/test.zip',
  success: (res) => {
    const { success } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "success": true }
```