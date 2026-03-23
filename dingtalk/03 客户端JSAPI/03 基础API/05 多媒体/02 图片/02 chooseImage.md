---
title: "chooseImage"
source: "https://open.dingtalk.com/document/development/jsapi-choose-image"
category: "客户端JSAPI / 基础API / 多媒体 / 图片"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-image_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-image_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用chooseImage，从本地相册选择图片。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.5.35 | 6.5.35 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10194) |
| 小程序 | 6.5.35 | 6.5.35 | 7.0.0 | 6.5.35 | 6.5.35 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10194) |

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
| count | Number | 否 | 9 | 最大可选照片数，默认值1张。  当sourceType参数内只有camera时，该参数只能传1。 |
| sourceType | Array<String> | 否 | ['camera','album'] | 相册选取或者拍照，默认 ['camera','album']。 |
| secret | Boolean | 否 | false | 相机拍照生成的图片，是否存储到私有目录。   * **true**：图片存储到本机的目录为`/data/user/0/com.alibaba.android.rimet/cache/lightapp/xxxxx.jpg`。 * **false**：图片存储到本机的目录为`/storage/emulated/0/Android/data/com.alibaba.android.rimet/cache/Pissarro/xxx.jpg`。   仅Android端并且钉钉客户端是6.5.27及以上版本支持。 |
| position | String | 否 | back | 相机拍照使用的摄像头：   * front：前置摄像头 * back：后置摄像头   * 默认back。 * 仅Android端并且钉钉客户端是6.5.27及以上版本支持。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| files | Array<Object> | [{"path":"https://resource/MzNjMmEwN2FjMjg0YTBkYTI4NTdlYmJhNTI3NDhlZWU=.image","size":327622,"fileType":"jpg"},{"path":"https://resource/ZDNmODkzM2RhNWQwMWI4NzEwOGFlY2U0NzJkY2ZmZjY=.image","size":317501,"fileType":"jpg"}] | 文件描述。 |
| filePaths | Array<String> | ["https://resource/MzNjMmEwN2FjMjg0YTBkYTI4NTdlYmJhNTI3NDhlZWU=.image","https://resource/ZDNmODkzM2RhNWQwMWI4NzEwOGFlY2U0NzJkY2ZmZjY=.image"] | 文件路径。 |

## **错误码**

| **错误码** | **描述** |
| --- | --- |
| 11 | 在开发者后台将此域名添加到安全域名列表中。 |

## **示例****代码**

### 默认出入参

```javascript
dd.chooseImage({
  count: 9,
  secret: false,
  position: 'back',
  sourceType: ['camera', 'album'],
  success: (res) => {
    const { files, filePaths } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "files": [
    {
      "path": "https://resource/MzNjMmEwN2FjMjg0YTBkYTI4NTdlYmJhNTI3NDhlZWU=.image",
      "size": 327622,
      "fileType": "jpg"
    },
    {
      "path": "https://resource/ZDNmODkzM2RhNWQwMWI4NzEwOGFlY2U0NzJkY2ZmZjY=.image",
      "size": 317501,
      "fileType": "jpg"
    }
  ],
  "filePaths": [
    "https://resource/MzNjMmEwN2FjMjg0YTBkYTI4NTdlYmJhNTI3NDhlZWU=.image",
    "https://resource/ZDNmODkzM2RhNWQwMWI4NzEwOGFlY2U0NzJkY2ZmZjY=.image"
  ]
}
```