---
title: "checkAuth"
source: "https://open.dingtalk.com/document/development/jsapi-check-auth"
category: "客户端JSAPI / 基础API / 设备 / 系统信息"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-check-auth_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-check-auth_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用checkAuth，检查手机权限授权状态。

检查钉钉是否获得某个权限的系统授权，如果没有获得，可以通过showAuthGuide引导用户授权。

| 枚举值 | 描述 |
| --- | --- |
| CAMERA | 相机 |
| PHOTO | 相册 |
| LBS | 地理位置 |
| BLUETOOTH | 蓝牙 |
| MICROPHONE | 麦克风 |
| ADDRESSBOOK | 通讯录 |
| NOTIFICATION | 通知栏权限 |
| SHORTCUT | 创建桌面快捷方式（仅Android） |

注意：

蓝牙权限 仅在iOS13.1及以上系统支持。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.0.0 | 7.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11621) |
| 小程序 | 7.0.10 | 7.0.10 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11621) |

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
| authType | String | 是 | PHOTO | 权限类型 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| granted | Boolean | true | 是否获得授权 |

## **示例****代码**

### 默认出入参

```javascript
dd.checkAuth({
  authType: 'PHOTO',
  success: (res) => {
    const { granted } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "granted": true }
```