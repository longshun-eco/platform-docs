---
title: "uploadFile"
source: "https://open.dingtalk.com/document/development/jsapi-upload-file"
category: "客户端JSAPI / 基础API / 网络 / 上传下载"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-upload-file_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-upload-file_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用uploadFile，上传本地资源到开发者服务器。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.0.10 | 7.0.10 | 7.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10281) |
| 小程序 | 7.0.10 | 7.0.10 | 7.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10281) |

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
| url | String | 是 | https://xxx.org/uploadFile | 开发者服务器地址。 |
| header | Object | 否 |  | HTTP 请求 Header。  \*\*注意：\*\*不携带cookie信息 |
| filePath | String | 是 | https://resource/apml31fc26337c885be15b4fd1c0abefee8f.image | 文件的虚拟地址，如[选择图片](https://open.dingtalk.com/document/orgapp/jsapi-chooseImage)方法获取的图片虚拟路径。 |
| fileName | String | 是 | xxx | 文件名，即对应的 key, 开发者在服务器端通过这个 key 可以获取到文件二进制内容。 |
| fileType | String | 是 | image | 文件类型：   * image：图片 * video：视频 * audio：音频 |
| formData | Object | 否 |  | HTTP 请求中其他额外的 form 数据。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| data | String | success | 服务器返回的数据。 |
| header | Object | {'content-type': 'application/json'} | 服务器返回的 header。 |
| statusCode | String | 200 | HTTP 状态码。 |

## **示例****代码**

### 默认出入参

```javascript
dd.uploadFile({
  url: 'https://xxx.org/uploadFile',
  header: {},
  fileName: 'xxx',
  filePath: 'https://resource/apml31fc26337c885be15b4fd1c0abefee8f.image',
  fileType: 'image',
  formData: {},
  success: (res) => {
    const { data, header, statusCode } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "data": "success",
  "header": { "content-type": "application/json" },
  "statusCode": "200"
}
```