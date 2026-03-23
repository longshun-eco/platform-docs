---
title: "uploadAttachmentToDingTalk"
source: "https://open.dingtalk.com/document/development/jsapi-upload-attachment-to-ding-talk"
category: "客户端JSAPI / 协同 / 钉盘"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-upload-attachment-to-ding-talk_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-upload-attachment-to-ding-talk_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用uploadAttachmentToDingTalk，上传附件到钉盘，或从钉盘选择文件。

## 使用说明

> 网页应用（H5微应用）使用前，先引入钉钉 js，参考[客户端SDK](https://open.dingtalk.com/document/orgapp/webapp-read-before-development)。

此接口支持照片、拍照、本地系统文件和从已有钉盘文件选择，返回值为文件在钉盘系统内的数据信息，如spaceId、fileId等。其中照片、拍照和本地系统文件将先上传到参数spaceId指定的钉盘空间再返回，上传过程对开发者透明。

存储空间/自定义空间：调用该 jsapi 前需要先创建存储空间并授予当前用户对该空间的上传操作权限，请参考[添加空间](https://open.dingtalk.com/document/orgapp/add-space)和[添加权限](https://open.dingtalk.com/document/orgapp/add-storage-permissions)。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10318) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10318) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

在H5应用中，调用[dd.config](https://open.dingtalk.com/document/orgapp/jsapi-authentication)完成鉴权后使用

在小程序应用中，无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| types | Array<String> | 是 | ["photo","camera","file","space"] | 支持上传附件的文件类型，至少一个：   * photo: 从手机相册选择图片上传到钉盘，再返回。 * camera: 用手机摄像头拍照上传到钉盘，再返回。 * file: android是“本地文件”， iOS表示从“文件”上传，再返回。 * space: 从钉盘直接选择文件返回。   * Android&iOS端：最多支持四种类型["photo","camera","file","space"]。 * PC端：最多支持["photo","file","space"]。 |
| image | Object | 否 | {multiple:true,compress:false,max:9,spaceId: "12345",folderId:"123"} | 从手机相册或者拍照上传，types这个数组里有photo、camera参数需要构建这个数据。 |
| file | Object | 是 | {spaceId:"12345",folderId:"123",max:1} | 从手机文件选择上传，types这个数组里有file参数需要构建这个数据。 |
| space | Object | 是 | {corpId:"xxx3020",spaceId:"12345",folderId:"123",isCopy:1 , max:9} | 从钉盘选择文件，types这个数组里有space参数需要构建这个数据。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| data | Object |  | 文件信息。 |
| type | String | image | 用户选择了哪种文件类型 ：   * image：图片 * file：手机文件 * space：钉盘文件 |

## **示例****代码**

### 默认出入参

```javascript
dd.uploadAttachmentToDingTalk({
  file: { max: 9, spaceId: '12345', folderId: '123' },
  image: {
    max: 9,
    spaceId: '12345',
    compress: true,
    folderId: '123',
    multiple: true,
  },
  space: {
    max: 9,
    corpId: 'ding1234xxx',
    isCopy: 1,
    spaceId: '12345',
    folderId: '123',
  },
  types: ['photo', 'camera', 'file', 'space'],
  success: (res) => {
    const { data, type } = res;
  },
  fail: () => {},
```

`success`返回对象示例：

```json
{
  "data": {
    "fileId": "DzzzzzzNqZY",
    "spaceId": "232323",
    "fileName": "审批流程.docx",
    "fileSize": "1024",
    "fileType": "docx"
  },
  "type": "image"
}
```