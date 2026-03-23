---
title: "获取文件或目录的status对象"
source: "https://open.dingtalk.com/document/development/obtain-the-file-status-object"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 文件管理器"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-obtain-the-file-status-object_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-the-file-status-object_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**FileSystemManager.stat**，获取文件或目录的status对象。

## **扫码体验**

![[development-obtain-the-file-status-object_p497732.png]]

## **使用说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **客户端** | **Android** | **iOS** | **PC** |
| 支持说明 | 支持(钉钉版本≥6.5.26) | 支持(钉钉版本≥6.5.25) | 不支持 |

## **示例代码**

```javascript
let fileManager = dd.getFileSystemManager();
 fileManager.stat({
      path: `${dd.env.USER_DATA_PATH}/newDir`,
      recursive:true,
      success: (res) => {
        console.log(res)
      },
      fail: (err) => {
        console.log(err)
      }
    })
```

## **入参说明**

|  |  |  |  |
| --- | --- | --- | --- |
| **参数** | **类型** | **是否必填** | **描述** |
| path | String | 是 | 源文件路径，可以是文件路径，也可以是目录路径。 |
| recursive | Boolean | 否 | 是否递归获取目录或文件的status对象。   * **true**：是 * **false**：否 |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Function | 否 | 调用结束的回调函数（调用成功、失败都会执行）。 |

## **返回结果**

### **成功**

|  |  |  |
| --- | --- | --- |
| **字段** | **类型** | **说明** |
| stats | Object | 返回的stats信息。   * 如果path是个目录路径。    + recursive值为false，返回的是path当前目录的status对象。   + recursive值为true，返回的是path当前目录下所有子目录和文件的status对象。 * 如果path是个文件路径，recursive值为false或true，返回的都是当前文件的status对象。 |
| mode | Long | 文件的类型和存储的权限。 |
| size | Long | 文件大小，单位Byte。 |
| lastAccessedTime | Long | 上次访问的时间戳，单位秒。 |
| lastModifiedTime | Long | 上次修改时间戳，单位秒。 |

### **失败**

|  |  |  |
| --- | --- | --- |
| **返回信息** | **类型** | **说明** |
| Object | Object | 错误信息。 |

## **错误码**

|  |  |  |
| --- | --- | --- |
| **errorCode** | **errorMessage** | **说明** |
| 10022 | 文件不存在 | path指定的文件路径错误。 |