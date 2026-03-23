---
title: "chooseFile"
source: "https://open.dingtalk.com/document/development/jsapi-choose-file"
category: "客户端JSAPI / 基础API / 文件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-file_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-file_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-12-08

选择本地文件。

调用dd.chooseFile，选择本地文件，返回其虚拟路径。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.1.5 | 7.1.5 | 不支持 | 7.1.10 | 7.1.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11736) |
| 小程序 | 7.1.5 | 7.1.5 | 不支持 | 7.1.10 | 7.1.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11736) |

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
| count | Number | 否 | 1 | 最多可以选择的文件个数，取值范围[1,9]，默认值1。 |
| multiSelection | Boolean | 否 | false | 是否允许多选，默认值false。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| files | Object |  | 文件对象。 |

## **示例****代码**

### 默认出入参

```
dd.chooseFile({
  count: 1,
  multiSelection: false,
});
```

返回对象示例：

```json
{
  "files": {
    "name": `name示例值`,
    "path": "https://resource/bc222c20be849b002903a686f3921a9f.file",
    "size": 84
  }
}
```