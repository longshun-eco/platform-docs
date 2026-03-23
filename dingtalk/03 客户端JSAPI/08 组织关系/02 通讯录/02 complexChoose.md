---
title: "complexChoose"
source: "https://open.dingtalk.com/document/development/jsapi-complex-choose"
category: "客户端JSAPI / 组织关系 / 通讯录"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-complex-choose_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-complex-choose_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用complexChoose，选择人和部门。

![[development-jsapi-complex-choose_O1CN01kfcX9r24hmoE66zrS_!!6000000007423-0-tps-536-1020.jpg]]

支持选择企业关联的上下游组织

![[development-jsapi-complex-choose_O1CN01POFp0q1yNjmI18vRD_!!6000000006567-0-tps-1164-1032.jpg]]

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10309) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10309) |

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
| corpId | String | 否 | ding1234xxxxx | 企业id。 |
| appId | String | 否 | 013324 | 三方应用使用appId，企业内部应用使用agentId。 |
| title | String | 否 | 选择员工 | 选择页面的标题。 |
| multiple | Boolean | 否 | true | 是否可多选：   * true: 可多选 * false：仅单选   默认仅单选（false）。 |
| limitTips | String | 否 | 选择人数不能超过20个 | 超过限定人数返回的提示内容。 |
| maxUsers | Number | 否 | 100 | 最大可选人数，最大值为10000。 |
| pickedUsers | Array<String> | 否 | ["userId0","userId2" ] | 已选用户的userId列表。  当`multiple`字段为false仅单选状态时，pickedUsers字段移动端不支持。 |
| pickedDepartments | Array<String> | 否 | ["deptId0","deptId1" ] | 已选的部门id列表。 |
| disabledUsers | Array<String> | 否 | ["userId0","userId2" ] | 不可选用户的userId列表。 |
| disabledDepartments | Array<String> | 否 | ["deptId0","deptId1" ] | 不可选部门id列表。 |
| requiredUsers | Array<String> | 否 | ["userId0","userId2" ] | 必选用户 (不可取消选中状态)。 |
| responseUserOnly | Boolean | 否 | true | 是否仅返回人员信息：   * true：仅返回人员信息 * false：返回人员和部门信息   默认为false。 |
| deptId | String | 否 | 0987 | 选择部门和人时的开始位置：   * -1：表示从企业根目录部门开始 * 0：表示从自己所在的部门开始   该参数只支持IOS端，Android端可使用startWithDepartmentId参数。 |
| rootPage | String | 否 |  | 初始页面是组织架构或组织列表页，默认为组织架构页（如示例图1）。可选填CommonOrgContact，组织列表页（如示例图2）。  此场景下corpId选填。 |
| showLabelPick | Boolean | 否 | true | 组织列表上是否展示按角色选择（如示例图2）。  PC 端暂不支持该参数。 |
| showOrgEcological | Boolean | 否 | false | 组织列表上是否展示组织关联的上下游组织入口（如 示例图2 框选入口）。 |
| filterOrgEcological | Boolean | 否 | false | 显示指定企业的上下游组织列表（如示例图3）。  请同时设置rootPage=CommonOrgContact，corpId必填。 |
| requiredDepartments | Array<String> | 否 | ["deptId0","deptId1" ] | 必选部门 (不可取消选中状态)。 |
| startWithDepartmentId | String | 否 | 0332 | 选择部门和人时的开始位置   * 0：表示从企业根目录开始 * -1：表示从自己所在部门开始   该参数只支持Android端，IOS端可使用deptId参数。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| users | Array<Object> |  |  |
| departments | Array<Object> |  |  |
| selectedCount | Number | 4 | 已选部门下的总人数和已选用户数的总和 |

## **示例****代码**

### 默认出入参

```
dd.complexChoose({
  appId: '013324',
  title: '选择员工',
  corpId: 'ding1234xxxxx',
  deptId: '0987',
  maxUsers: 100,
  multiple: true,
  rootPage: `rootPage示例值`,
  limitTips: '选择人数不能超过20个',
  pickedUsers: ['userId0', 'userId2'],
  disabledUsers: ['userId0', 'userId2'],
  requiredUsers: ['userId0', 'userId2'],
  showLabelPick: true,
  responseUserOnly: true,
  pickedDepartments: ['deptId0', 'deptId1'],
  showOrgEcological: false,
  disabledDepartments: ['deptId0', 'deptId1'],
  filterOrgEcological: false,
  requiredDepartments: ['deptId0', 'deptId1'],
  startWithDepartmentId: '0332',
  success: (res) => {
```

`success`返回对象示例：

```json
{
  "users": [
    {
      "name": "钉小二",
      "avatar": "https://static.dingtalk.com/media/lADPDiCpu12oVqvNApTNApQ_660_660.jpg",
      "emplId": "22055215283702319x"
    }
  ],
  "departments": [{ "id": "68094649x", "name": "人事部", "number": 10 }],
  "selectedCount": 4
}
```