---
title: "getCloudCallList"
source: "https://open.dingtalk.com/document/development/jsapi-get-cloud-call-list"
category: "客户端JSAPI / 音视频 / 办公电话"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-cloud-call-list_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-cloud-call-list_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用getCloudCallList，查询话单列表。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 6.0.9 | 6.0.9 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11648) |
| 小程序 | 6.0.0 | 6.0.0 | 6.0.9 | 6.0.9 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11648) |

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
| index | Number | 是 | 0 | 起始页，从0开始。 |
| corpId | String | 是 | ding1234 | 当前企业的corpId。 |
| endTime | String | 是 | 2022-02-01 00:00:00 | 结束时间，格式为yyyy-MM-dd HH:mm:ss。 |
| pageSize | Number | 是 | 100 | 每页个数，最大值100。 |
| sessionId | String | 否 | 798xxxxx | 会话ID。 |
| bizNumber | String | 否 | 711xxxxx | 外呼的被叫号码。 |
| startTime | String | 是 | 2022-01-01 00:00:00 | 开始时间，格式为yyyy-MM-dd HH:mm:ss。 |
| staffIdList | Array<String> | 否 | ["userId1","userId2"] | 指定查询的userId列表。 |
| direction | Number | 是 | 1 | 电话类型，默认是0：   * 0：外呼 * 1：呼入 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| code | Number | 200 | 返回码。 |
| cause | String | 内部异常 | 异常描述。 |
| total | Number | 10 | 总条数。 |
| hasMore | Boolean | true | 是否还有下一页。 |
| callList | Array<String> | ["711xxxxx","711xxxxx"] | 话单列表。 |
| currentIndex | Number | 2 | 当前页码。 |

## **示例****代码**

### 默认出入参

```javascript
dd.getCloudCallList({
  index: 0,
  corpId: 'ding1234',
  endTime: '2022-02-01 00:00:00',
  pageSize: 100,
  bizNumber: '711xxxxx',
  direction: 1,
  sessionId: '798xxxxx',
  startTime: '2022-01-01 00:00:00',
  staffIdList: ['userId1', 'userId2'],
  success: (res) => {
    const { code, cause, total, hasMore, callList, currentIndex } = res;
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
  "total": 10,
  "hasMore": true,
  "callList": ["711xxxxx", "711xxxxx"],
  "currentIndex": 2
}
```