---
title: "chooseDepartments"
source: "https://open.dingtalk.com/document/development/jsapi-choose-departments"
category: "客户端JSAPI / 组织关系 / 通讯录"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-departments_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-departments_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用chooseDepartments，返回部门的信息，是以部门为纬度，不是以人为纬度。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10310) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10310) |

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
| limitTips | String | 否 | 选择数量不能超过20个 | 超过限定数量返回的提示内容。 |
| maxDepartments | Number | 否 | 100 | 最大可选部门数。 |
| pickedDepartments | Array<String> | 否 | ["deptId0","deptId1" ] | 已选的部门id。 |
| disabledDepartments | Array<String> | 否 | ["deptId0","deptId1" ] | 不可选的部门id。 |
| requiredDepartments | Array<String> | 否 | ["deptId0","deptId1" ] | 必选部门 (不可取消选中状态)。 |
| appId | String | 否 |  | 微应用agentId。  H5应用必填。 |
| corpId | String | 否 |  | 企业的corpId。  H5应用必填。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| userCount | Number | 5 | 所选部门下所有员工的数量。 |
| departments | Array<Object> |  |  |
| departmentsCount | Number | 2 | 所选部门的数量。 |

## **示例****代码**

### 默认出入参

```javascript
dd.chooseDepartments({
  appId: `appId示例值`,
  title: '标题',
  corpId: `corpId示例值`,
  multiple: true,
  limitTips: '选择数量不能超过20个',
  maxDepartments: 100,
  pickedDepartments: ['deptId0', 'deptId1'],
  disabledDepartments: ['deptId0', 'deptId1'],
  requiredDepartments: ['deptId0', 'deptId1'],
  success: (res) => {
    const { userCount, departments, departmentsCount } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "userCount": 5,
  "departments": [{ "id": "68094649x", "name": "人事部", "number": 10 }],
  "departmentsCount": 2
}
```