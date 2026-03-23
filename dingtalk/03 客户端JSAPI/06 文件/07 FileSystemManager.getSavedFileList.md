---
title: "FileSystemManager.getSavedFileList"
source: "https://open.dingtalk.com/document/development/jsapi-file-system-manager-get-saved-file-list"
category: "客户端JSAPI / 文件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-file-system-manager-get-saved-file-list_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-file-system-manager-get-saved-file-list_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用FileSystemManager.getSavedFileList，获取本地缓存文件列表。

> 本接口获取的是调用保存文件接口保存为本地缓存的文件，保存为本地用户的文件不支持获取。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10268) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| success | Boolean | true | 成功获取本地缓存文件列表时，返回true。 |
| fileList | Array<Object> |  | 本地缓存的文件列表。 |

## **示例****代码**

### 默认出入参

```javascript
const fileSystemManager = dd.getFileSystemManager();

fileSystemManager.getSavedFileList({
  success: (res) => {
    const { success, fileList } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "success": true,
  "fileList": [
    {
      "size": 10,
      "filePath": "本地缓存文件的路径示例值",
      "createTime": 1688350073000
    }
  ]
}
```