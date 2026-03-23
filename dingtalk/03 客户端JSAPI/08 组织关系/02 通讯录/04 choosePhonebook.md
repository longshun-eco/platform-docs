---
title: "choosePhonebook"
source: "https://open.dingtalk.com/document/development/jsapi-choose-phonebook"
category: "客户端JSAPI / 组织关系 / 通讯录"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-phonebook_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-phonebook_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用choosePhonebook，选取用户手机联系人。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10307) |
| 小程序 | 6.0.0 | 6.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10307) |

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
| title | String | 否 | 标题 | 选择页面的标题。 |
| multiple | Boolean | 否 | true | 是否可多选：   * true: 可多选 * false：仅单选   默认仅单选（false）。 |
| maxUsers | Number | 否 | 20 | 最大可选人数。 |
| limitTips | String | 否 | 选择人数不能超过20个 | 超过限定人数返回的提示内容。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| name | String | 妈妈 | 联系人名称。 |
| mobile | String | 1340000000 | 联系人手机号。 |
| mediaId | String | @lQDPDht0xzDn82rNA3PNA3KwFFY1idqwQ4ICkACePMAgAA | 联系人头像图片的mediaId。 |

## **示例****代码**

### 默认出入参

```javascript
dd.choosePhonebook({
  title: '标题',
  maxUsers: 20,
  multiple: true,
  limitTips: '选择人数不能超过20个',
  success: (res) => {
    const { name, mobile, mediaId } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "name": "妈妈",
  "mobile": "1340000000",
  "mediaId": "@lQDPDht0xzDn82rNA3PNA3KwFFY1idqwQ4ICkACePMAgAA"
}
```