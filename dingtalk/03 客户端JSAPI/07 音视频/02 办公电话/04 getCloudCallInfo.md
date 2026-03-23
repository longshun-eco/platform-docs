---
title: "getCloudCallInfo"
source: "https://open.dingtalk.com/document/development/jsapi-get-cloud-call-info"
category: "客户端JSAPI / 音视频 / 办公电话"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-cloud-call-info_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-cloud-call-info_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用getCloudCallInfo，查询企业是否已开办公电话。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11650) |
| 小程序 | 6.0.0 | 6.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11650) |

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
| corpId | String | 是 | ding1234xxx | 当前企业的corpId。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| code | Number | 200 | 返回码，200表示正常。 |
| cause | String | 内部异常 | 异常描述。 |
| hasOpen | Boolean | true | 是否开户。 |
| bizNumberList | Array<String> | ['711xxxxx','712xxxxx'] | 开户的电话号码。 |

## **示例****代码**

### 默认出入参

```javascript
dd.getCloudCallInfo({
  corpId: 'ding1234',
  success: (res) => {
    const { code, cause, hasOpen, bizNumberList } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "code": 200,
  "cause": "内部异常",
  "hasOpen": true,
  "bizNumberList": ["711xxxxx", "712xxxxx"]
}
```