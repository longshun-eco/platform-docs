---
title: "chooseUserFromList"
source: "https://open.dingtalk.com/document/development/jsapi-choose-user-from-list"
category: "客户端JSAPI / 组织关系 / 通讯录"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-user-from-list_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-user-from-list_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用chooseUserFromList，选取单个自定义联系人。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11505) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11505) |

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
| users | Array<String> | 是 | ["userId0","userId2" ] | 自定义可以选择对的用户的userId列表。 |
| isShowCompanyName | Boolean | 否 | true | 是否显示公司名称。 |
| disabledUsers | Array<String> | 否 | ["userId0","userId2" ] | 不可选用户的userId列表。 |
| corpId | String | 否 |  | 企业corpId。  在H5应用中必填。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```javascript
dd.chooseUserFromList({
  title: '标题',
  users: ['userId0', 'userId2'],
  corpId: `corpId示例值`,
  disabledUsers: ['userId0', 'userId2'],
  isShowCompanyName: true,
  success: (res) => {
    const { name, avatar, userId } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "name": "钉小二",
  "avatar": "https://static.dingtalk.com/media/lADPDiCpu12oVqvNApTNApQ_660_660.jpg",
  "userId": "22055215283702319x"
}
```