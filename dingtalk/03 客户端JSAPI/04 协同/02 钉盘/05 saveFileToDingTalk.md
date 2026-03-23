---
title: "saveFileToDingTalk"
source: "https://open.dingtalk.com/document/development/jsapi-save-file-to-ding-talk"
category: "客户端JSAPI / 协同 / 钉盘"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-save-file-to-ding-talk_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-save-file-to-ding-talk_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用saveFileToDingTalk，转存文件到钉盘。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10316) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10316) |

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
| url | String | 是 | https://ringnerippca.files.wordpress.com/20.pdf | 文件在第三方服务器上的url地址或通过单步文件上传获取到的media\_id。  如果是url地址，要求资源请求返回消息头中需要包含Content-Length字段，且>0。 |
| name | String | 是 | 大合照.png | 文件保存的名字。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| data | Array<Object> |  | 文件数据。 |

## **示例****代码**

### 默认出入参

```javascript
dd.saveFileToDingTalk({
  url: 'https://ringnerippca.files.wordpress.com/20.pdf',
  name: '大合照.png',
  success: (res) => {
    const { data } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "data": [
    {
      "fileId": "3333",
      "spaceId": "xxxx",
      "fileName": "集体合照.png",
      "fileSize": "1024",
      "fileType": "png"
    }
  ]
}
```