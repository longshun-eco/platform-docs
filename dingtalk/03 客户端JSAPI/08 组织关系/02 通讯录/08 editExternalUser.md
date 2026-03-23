---
title: "editExternalUser"
source: "https://open.dingtalk.com/document/development/jsapi-edit-external-user"
category: "客户端JSAPI / 组织关系 / 通讯录"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-edit-external-user_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-edit-external-user_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用editExternalUser，编辑外部联系人。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10312) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10312) |

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
| title | String | 否 | 添加外部联系人 | 编辑页面的标题。 |
| emplId | String | 否 | 09888 | 需要编辑的外部联系人的userId；不填，则为新增外部联系人。 |
| name | String | 否 | 钉小二 | 需要新增的外部联系人的名字。 |
| mobile | String | 否 | 13800000000 | 需要预填的手机号。 |
| companyName | String | 否 | 钉钉 | 需要预填的公司名。 |
| deptName | String | 否 | 人事部 | 预填部门名字。 |
| job | String | 否 | 总监 | 预填职位。 |
| remark | String | 否 | 人事部一号位 | 备注信息。 |
| corpId | String | 否 | ding12345 | 企业corpId。  H5应用必填。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| userId | String | 09888 | 外部联系人的userId。 |
| name | String | 钉小二 | 外部联系人的姓名。 |
| mobile | String | 13800000000 | 外部联系人的电话。 |
| companyName | String | 钉钉 | 外部联系人的的公司名。 |
| deptName | String | 人事部 | 外部联系人的部门。 |
| job | String | 总监 | 外部联系人的职位。 |
| remark | String | 人事部一号位 | 外部联系人的备注信息。 |

## **示例****代码**

### 默认出入参

```javascript
dd.editExternalUser({
  job: '总监',
  name: '钉小二',
  title: '添加外部联系人',
  corpId: 'ding12345',
  emplId: '09888',
  mobile: '13800000000',
  remark: '人事部一号位',
  deptName: '人事部',
  companyName: '钉钉',
  success: (res) => {
    const { job, name, mobile, remark, userId, deptName, companyName } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "job": "总监",
  "name": "钉小二",
  "mobile": "13800000000",
  "remark": "人事部一号位",
  "userId": "09888",
  "deptName": "人事部",
  "companyName": "钉钉"
}
```