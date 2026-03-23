---
title: "addPhoneContact"
source: "https://open.dingtalk.com/document/development/jsapi-add-phone-contact"
category: "客户端JSAPI / 基础API / 设备 / 拨打电话"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-add-phone-contact_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-add-phone-contact_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用addPhoneContact，添加手机联系人。

用户可以选择将表单以“创建新联系人”或“添加到现有联系人”的方式，写入联系人资料到手机系统的通讯录。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11626) |
| 小程序 | 7.0.10 | 7.0.10 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11626) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| name | String | 是 |  | 姓名。 |
| email | String | 否 |  | 电子邮件。 |
| remark | String | 否 |  | 备注。 |
| address | String | 否 |  | 联系地址。 |
| phoneNumber | String | 是 |  | 手机号。 |
| photoFilePath | String | 否 |  | 头像本地文件路径。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| success | Boolean | true | 是否添加成功。 |

## **示例****代码**

### 默认出入参

```javascript
dd.addPhoneContact({
  name: `name示例值`,
  email: `email示例值`,
  remark: `remark示例值`,
  address: `address示例值`,
  phoneNumber: `phoneNumber示例值`,
  photoFilePath: `photoFilePath示例值`,
  success: (res) => {
    const { success } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "success": true }
```