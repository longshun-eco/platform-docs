---
title: "editPicture"
source: "https://open.dingtalk.com/document/development/jsapi-edit-picture"
category: "客户端JSAPI / 基础API / 多媒体 / 图片"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-edit-picture_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-edit-picture_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用editPicture，编辑图片。

> 支持远程 https 图片地址和本地虚拟路径，提供涂鸦、裁剪、马赛克等功能。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10199) |

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
| url | String | 是 | https://gw.alicdn.com/imgextra/i3/O1CN01Eg6xCm1nnsXZCnkP4\_!!6000000005135-2-tps-200-200.png | 图片的远端路径或者本地路径。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| path | String | https://resource/427842e730ca5187d9275681e4968f99.image | 编辑后的本地文件路径。 |

## **错误码**

| **错误码** | **描述** |
| --- | --- |
| 2 | 参数无效 |
| 3 | 系统异常 |
| -1 | 用户取消 |
| 1 | 当前端不支持此API |

## **示例****代码**

### 默认出入参

```javascript
dd.editPicture({
  url: 'https://gw.alicdn.com/imgextra/i3/O1CN01Eg6xCm1nnsXZCnkP4_!!6000000005135-2-tps-200-200.png',
  success: (res) => {
    const { path } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "path": "https://resource/427842e730ca5187d9275681e4968f99.image" }
```