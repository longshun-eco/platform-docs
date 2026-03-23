---
title: "DING"
source: "https://open.dingtalk.com/document/development/ding-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 开放接口"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-ding-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-ding-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.createDing**发起DING。

发钉接口支持唤起DING、任务、日程等创建界面。

目前发钉只支持客户端发钉，不支持直接通过服务端发钉。

## 示例代码

```
dd.createDing({
    users: ["0314170369704678"], //默认选中用户工号列表；类型: Array
    corpId: "dingb7axxxxxx35c2f4657eb6378f", // 类型: String
    alertType: 2, // 钉发送方式 0:电话, 1:短信, 2：应用内；类型 Number
    alertDate: {"format":"yyyy-MM-dd HH:mm", "value":"2019-08-29 08:25"}, // 非必选，定时发送时间, 非定时DING不需要填写
    type: 1,// 附件类型 1：image, 2：link；类型: Number

    // 非必选
    // 附件信息
    attachment: {
       images: ["https://www.baidu.com/img/bd_logo1.png?where=super"], // 图片附件, type=1时, 必选；类型: Array
       image: "https://www.baidu.com/img/bd_logo1.png?where=super", // 链接附件, type=2时, 必选；类型: String
       title: "这是一个测试", // 链接附件, type=2时, 必选；类型: String
       url: "https://www.baidu.com/", // 链接附件, type=2时, 必选；类型 String
       text: "测试发钉成功" // 链接附件, type=2时, 必选；类型: String
    },

    text: '',  // 正文
    bizType :0, // 业务类型 0：通知DING；1：任务；2：会议；

    // 任务信息
```

## 入参

| **参数** | **类型** | **说明** |
| --- | --- | --- |
| users | String[] | 用户列表，员工userid。 |
| corpId | String | 企业corpId。 |
| alertType | Number | 钉提醒类型：   * **0**：电话 * **1**：短信 * **2**：应用内 |
| alertDate | Object | 钉提醒时间；非必填。 |
| type | Number | Number为整数，钉类型。   * **1**：image * **2**：link |
| attachment | Object | 附件信息。 |
| text | String | 消息体。 |
| bizType | Number | * **0**：通知DING * **1**：任务 * **2**：日程 |
| taskInfo | Object | 任务信息。 |
| confInfo | Object | 日程信息。 |

## 返回结果

| **参数** | **说明** |
| --- | --- |
| dingId | 发送的DING消息的id。 |
| text | 发送的DING消息的文本内容。 |
| result | 发送消息是否成功，true/false。 |