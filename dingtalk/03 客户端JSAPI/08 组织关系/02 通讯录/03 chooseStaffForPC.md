---
title: "chooseStaffForPC"
source: "https://open.dingtalk.com/document/development/jsapi-choose-staff-for-pc"
category: "客户端JSAPI / 组织关系 / 通讯录"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-staff-for-pc_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-staff-for-pc_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用chooseStaffForPC，PC端选择企业内部的人。

> 此接口只能选人，不能选择部门。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11657) |
| 小程序 | 不支持 | 不支持 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11657) |

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
| max | Number | 否 | 20 | 最大可选人数。 |
| users | Array<String> | 否 | ["userId0","userId2" ] | 已选用户的userId列表。 |
| corpId | String | 是 | ding1234xxxxx | 企业id。 |
| multiple | Boolean | 否 | true | 是否可多选。   * true: 可多选 * false：仅单选   默认仅单选（false）。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| name | String | 钉小二 | 用户名。 |
| avatar | String | https://static.dingtalk.com/media/lADPDiCpu12oVqvNApTNApQ\_660\_660.jpg | 用户头像。 |
| emplId | String | 22055215283702319x | 员工工号。 |

## **示例****代码**

### 默认出入参

```javascript
dd.chooseStaffForPC({
  max: 20,
  users: ['userId0', 'userId2'],
  corpId: 'ding1234xxxxx',
  multiple: true,
  success: (res) => {
    const { name, avatar, emplId } = res;
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
  "emplId": "22055215283702319x"
}
```