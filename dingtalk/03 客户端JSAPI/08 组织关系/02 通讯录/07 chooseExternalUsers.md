---
title: "chooseExternalUsers"
source: "https://open.dingtalk.com/document/development/jsapi-choose-external-users"
category: "客户端JSAPI / 组织关系 / 通讯录"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-external-users_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-external-users_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用chooseExternalUsers，选择外部联系人。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10311) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10311) |

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
| title | String | 否 | 选择员工 | 选择页面的标题。 |
| multiple | Boolean | 否 | true | 是否可多选：   * true: 可多选 * false：仅单选   默认仅单选。 |
| limitTips | String | 否 | 选择人数不能超过20个 | 超过限定人数返回的提示内容。 |
| maxUsers | Number | 否 | 100 | 最大可选人数，最大值为10000。 |
| pickedUsers | Array<String> | 否 | ["userId0","userId2" ] | 已选用户的userId列表。 |
| disabledUsers | Array<String> | 否 | ["userId0","userId2" ] | 不可选用户的userId列表。 |
| requiredUsers | Array<String> | 否 | ["userId0","userId2" ] | 必选用户。  不可取消选中状态。 |
| corpId | String | 否 | ding12345 | 企业corpId。  H5应用必填。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| 出参 | Array<Object> |  |  |

## **示例****代码**

### 默认出入参

```
dd.chooseExternalUsers({
  title: '选择员工',
  corpId: 'ding12345',
  maxUsers: 100,
  multiple: true,
  limitTips: '选择人数不能超过20个',
  pickedUsers: ['userId0', 'userId2'],
  disabledUsers: ['userId0', 'userId2'],
  requiredUsers: ['userId0', 'userId2'],
  success: (res) => {
    // res: [{name: '钉小二',avatar: 'https://static.dingtalk.com/media/lADPDiCpu12oVqvNApTNApQ_660_660.jpg',userId: '22055215283702319x',orgName: '钉钉',}]
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
[
  {
    "name": "钉小二",
    "avatar": "https://static.dingtalk.com/media/lADPDiCpu12oVqvNApTNApQ_660_660.jpg",
    "userId": "22055215283702319x",
    "orgName": "钉钉"
  }
]
```