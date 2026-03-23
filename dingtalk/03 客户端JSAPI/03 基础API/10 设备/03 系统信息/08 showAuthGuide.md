---
title: "showAuthGuide"
source: "https://open.dingtalk.com/document/development/jsapi-show-auth-guide"
category: "客户端JSAPI / 基础API / 设备 / 系统信息"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-show-auth-guide_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-show-auth-guide_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用showAuthGuide，授权引导。

弹出图文提示对话框，引导用户打开并授予钉钉指定权限。

部分 API（如 dd.chooseImage、dd.chooseLocation 等）或功能涉及手机上特定设备/隐私数据的使用，需要用户在系统设置里开启相关功能/授权给钉钉。如果相关权限缺失，而该权限对于应用的使用又不可缺少，建议使用 showAuthGuide 给予用户引导。

可通过checkAuth查看是否已授权。

支持的authType：

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

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.0.10 | 7.0.10 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11620) |
| 小程序 | 7.0.10 | 7.0.10 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11620) |

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
| authType | String | 是 | authType示例值 | 引导的权限标识，用于标识该权限类型。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| shown | Boolean | true | 是否已显示引导授权弹框。 |

## **示例****代码**

### 默认出入参

```javascript
dd.showAuthGuide({
  authType: 'authType示例值',
  success: (res) => {
    const { shown } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "shown": true }
```