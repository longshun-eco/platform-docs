---
title: "httpRequest"
source: "https://open.dingtalk.com/document/development/jsapi-http-request"
category: "客户端JSAPI / 基础API / 网络 / 发网络请求"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-http-request_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-http-request_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用dd.httpRequest向指定服务器发起一个跨域 http(s) 请求。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10280) |

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
| url | String | 是 | http://httpbin.org/post | 目标服务器url。 |
| data | Object | 否 |  | 请求参数。 |
| headers | Object | 否 | {'Content-Type': 'application/x-www-form-urlencoded'} | 设置请求的 HTTP 头，默认 {'Content-Type': 'application/x-www-form-urlencoded'}。 |
| method | String | 否 | POST | 默认GET，目前支持GET和POST。 |
| timeout | Number | 否 | 30000 | 超时时间，单位ms，默认30000。 |
| dataType | String | 否 | json | 期望返回的数据格式，默认json，支持json、text、base64。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| data | String | {} | 响应数据，格式取决于请求时的 dataType 参数。 |
| status | Number | 200 | 响应码。 |
| headers | Object | {'Content-Type': 'application/x-www-form-urlencoded'} | 响应头。 |

## **错误码**

| **错误码** | **描述** |
| --- | --- |
| 4 | 在开发者后台将上传URL设置为http安全域名。 |
| 11 | 在开发者后台将此域名添加到安全域名列表中。 |
| 12 | 由网络原因导致的错误，如网络不通等。 |
| 13 | http请求超时出现此类错误。 |
| 14 | httpRequest会根据dataType设置的类型自动对返回内容解码，解码失败时会出现此类错误。出现此类错误时，需要确定http请求返回的内容格式是否与dataType设置的类型一致。比如，当dataType类型为json时，httpRequest会将返回内容认定为json字符串，自动对内容做JSON.parse类操作，其他dataType类型类似。如果开发过程中不确定http返回内容是否OK，可以手动设置dataType为text，来查看http返回的内容。 |
| 19 | 异常http状态码错误。如500等接口异常。 |

## **示例****代码**

### 默认出入参

```javascript
dd.httpRequest({
  url: 'http://httpbin.org/post',
  data: {},
  method: 'POST',
  headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
  timeout: 30000,
  dataType: 'json',
  success: (res) => {
    const { data, status, headers } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "data": "{}",
  "status": 200,
  "headers": { "Content-Type": "application/x-www-form-urlencoded" }
}
```