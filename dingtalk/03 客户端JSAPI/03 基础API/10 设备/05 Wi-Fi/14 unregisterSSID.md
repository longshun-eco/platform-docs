---
title: "unregisterSSID"
source: "https://open.dingtalk.com/document/development/jsapi-unregister-ssid"
category: "客户端JSAPI / 基础API / 设备 / Wi-Fi"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-unregister-ssid_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-unregister-ssid_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

不再信任该 SSID(iOS)。

对于需要 Portal 认证的 Wi-Fi，继续弹出 portal 认证页面。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 不支持 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11479) |

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
| SSID | String | 是 |  | SSID |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| ![[development-jsapi-unregister-ssid_O1CN019V5Laa1JL54vlyQ2F_!!6000000001011-2-tps-360-360.png]] 暂无内容 | | | |

## **错误码**

| **错误码** | **描述** |
| --- | --- |
| 3 | 系统异常 |

## **示例****代码**

### 默认出入参

```javascript
dd.unregisterSSID({
  SSID: `SSID示例值`,
  success: (res) => {
    const {} = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{}
```