---
title: "FileSystemManager.stat"
source: "https://open.dingtalk.com/document/development/jsapi-file-system-manager-stat"
category: "客户端JSAPI / 文件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-file-system-manager-stat_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-file-system-manager-stat_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用FileSystemManager.stat，获取文件或目录的status对象。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.5.26 | 6.5.26 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10279) |

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
| path | String | 是 | ${dd.env.USER\_DATA\_PATH}/newDir | 源文件路径，可以是文件路径，也可以是目录路径。 |
| recursive | Boolean | 否 | true | 是否递归获取目录或文件的status对象：   * true：是 * false：否 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| stats | Object | {} | 返回的stats信息。  如果path是个目录路径：   * recursive值为false，返回的是path当前目录的status对象。 * recursive值为true，返回的是path当前目录下所有子目录和文件的status对象。  如果path是个文件路径，recursive值为false或true，返回的都是当前文件的status对象。 |
| mode | Number | 777 | 文件的类型和存储的权限。 |
| size | Number | 100 | 文件大小，单位Byte。 |
| lastAccessedTime | Number | 1000 | 上次访问的时间戳，单位秒。 |
| lastModifiedTime | Number | 10000 | 上次修改时间戳，单位秒。 |

## **示例****代码**

### 默认出入参

```javascript
const fileSystemManager = dd.FileSystemManager();

fileSystemManager.stat({
  path: '${dd.env.USER_DATA_PATH}/newDir',
  recursive: true,
  success: (res) => {
    const { mode, size, stats, lastAccessedTime, lastModifiedTime } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "mode": 777,
  "size": 100,
  "stats": {},
  "lastAccessedTime": 1000,
  "lastModifiedTime": 10000
}
```