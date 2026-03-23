---
title: "createDing"
source: "https://open.dingtalk.com/document/development/jsapi-create-ding"
category: "客户端JSAPI / 即时通讯IM / DING"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-create-ding_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-create-ding_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用createDing，发起DING。

发钉接口支持唤起DING、任务、日程等创建界面

> 目前发钉只支持客户端发钉，不支持直接通过服务端发钉。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10313) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10313) |

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
| users | Array<String> | 是 | ["03333", "04333"] | 需要发送到的用户的userid列表。 |
| type | Number | 否 | 1 | 附件类型：   * 1：图片 * 2：链接 |
| alertType | Number | 否 | 1 | 钉提醒类型：   * 0：电话 * 1：短信 * 2：应用内 |
| alertDate | Object | 否 |  | 钉提醒时间 |
| attachment | Object | 否 |  | 附件信息。 |
| text | String | 否 | 钉消息内容 | 消息体。 |
| confInfo | Object | 否 |  | 会议信息。 |
| corpId | String | 否 | ding\*\* | 企业corpId。  H5微应用必填。 |
| taskInfo | Object | 否 |  | 任务信息。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.createDing({
  text: '钉消息内容',
  type: 1,
  users: ['03333', '04333'],
  corpId: `corpId示例值`,
  confInfo: {
    endTime: { value: '2015-05-09 08:00', format: 'yyyy-MM-dd HH:mm' },
    location: `location示例值`,
    startTime: { value: '2015-05-09 08:00', format: 'yyyy-MM-dd HH:mm' },
    bizSubType: 27,
    remindType: 2,
    remindMinutes: 30,
  },
  taskInfo: {
    ccUsers: ['100', '101'],
    taskRemind: 30,
    deadlineTime: { value: '2015-05-09 08:00', format: 'yyyy-MM-dd HH:mm' },
  },
  alertDate: { value: '2015-05-09 08:00', format: 'yyyy-MM-dd HH:mm' },
  alertType: 1,
  attachment: { images: ['https://xxx.com/example1.png'] },
```