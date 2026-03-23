---
title: "openPageInMicroApp"
source: "https://open.dingtalk.com/document/development/jsapi-open-page-in-micro-app"
category: "客户端JSAPI / 基础API / 跳转"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-open-page-in-micro-app_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-open-page-in-micro-app_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用openPageInMicroApp，打开应用内页面

目前支持以下页面

* 个人资料页

```
// 页面名称：
  profile
// 传参：
    id:用户userId //String
    corpId:'' //企业id
```

* 聊天页面

```
// 页面名称：
    chat
// 传参：
    users: ['123'] 用户列表,工号
    corpId: '' //企业id
```

* 免费电话页面

```
// 页面名称：
    call
// 传参：
```

* 联系人添加页面

```
// 页面名称：
    contactAdd
// 传参：
```

* 唤起添加好友页面

```
// 页面名称：
    friendAdd
// 传参：
```

* 唤起员工管理页面

```
// 页面名称：
    manageOrg
// 传参：
"corpId":"dingd90ce2ec337f2f13", "isManager": "true"
```

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11693) |
| 小程序 | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

调用[dd.config](https://open.dingtalk.com/document/orgapp/jsapi-authentication)完成鉴权后使用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| name | String | 是 | profile | 页面名称。 |
| params | Object | 是 |  | 参数对象。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 打开个人资料页

```
dd.openPageInMicroApp({
  name: 'profile',
  params: {
    id: '用户userId',
    corpId: '',
  },
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```

### 打开聊天页面

```
dd.openPageInMicroApp({
  name: 'chat',
  params: {
    users: ['123'],
    corpId: '',
  },
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```