---
title: "downloadFile"
source: "https://open.dingtalk.com/document/development/jsapi-download-file"
category: "客户端JSAPI / 基础API / 网络 / 上传下载"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-download-file_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-download-file_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用downloadFile，下载文件资源到本地。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.0.10 | 7.0.10 | 7.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10282) |
| 小程序 | 7.0.10 | 7.0.10 | 7.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10282) |

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
| url | String | 是 | https://gw.alicdn.com/imgextra/i3/O1CN01Eg6xCm1nnsXZCnkP4\_!!6000000005135-2-tps-200-200.png | 下载文件地址。 |
| header | Object | 否 | {'content-type': 'image/jpeg'} | HTTP 请求 Header。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| filePath | String | https://resource/apml31fc26337c885be15b4fd1c0abefee8f.image | 文件临时存放的位置。 |

## **示例****代码**

### 默认出入参

```javascript
dd.downloadFile({
  url: 'https://gw.alicdn.com/imgextra/i3/O1CN01Eg6xCm1nnsXZCnkP4_!!6000000005135-2-tps-200-200.png',
  header: { 'content-type': 'image/jpeg' },
  success: (res) => {
    const { filePath } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "filePath": "https://resource/apml31fc26337c885be15b4fd1c0abefee8f.image" }
```