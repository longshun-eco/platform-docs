---
title: "rsa"
source: "https://open.dingtalk.com/document/development/jsapi-rsa"
category: "客户端JSAPI / 基础API / 设备 / 系统信息"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-rsa_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-rsa_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用rsa，实现rsa加解密。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.0.0 | 7.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11619) |
| 小程序 | 7.0.10 | 7.0.10 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11619) |

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
| key | String | 是 | key示例值 | RSA 密钥。PKCS8 格式。 加密使用公钥，解密使用私钥。 |
| text | String | 是 | text示例值 | 算法输入。加密时传入明文，解密时传入密文（base64 编码）。RSA key 为 1024 位时，最多支持 117 个字节。 |
| action | String | 是 | action示例值 | 使用 RSA 加密还是 RSA 解密。可选值：encrypt / decrypt |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| text | String | result示例值 | 算法输出。加密时得到密文（base64 编码），解密时得到明文。 |

## **示例****代码**

### 默认出入参

```javascript
dd.rsa({
  key: 'key示例值',
  text: 'text示例值',
  action: 'action示例值',
  success: (res) => {
    const { text } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "text": "result示例值" }
```