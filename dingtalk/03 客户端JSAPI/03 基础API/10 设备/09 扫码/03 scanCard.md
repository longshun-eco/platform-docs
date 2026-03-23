---
title: "scanCard"
source: "https://open.dingtalk.com/document/development/jsapi-scan-card"
category: "客户端JSAPI / 基础API / 设备 / 扫码"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-scan-card_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-scan-card_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用scanCard扫名片。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11698) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11698) |

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

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| ADDRESS | String | 深圳市南山区软件产业基地 | 地址。 |
| COMPANY | String | 深圳市\*\*科技有限公司 | 公司。 |
| NAME | String | \*\* | 姓名。 |
| MPHONE | String | 861333567890 | 手机号。 |
| PHONE | String | 01087654321 | 电话。 |
| IMAGE | String | http://www.taobao.com/xxx.jpg | 名片图片地址，可供用户手动上传名片。 |
| POSITION | String | CEO | 职位。 |

## **示例****代码**

### 默认出入参

```javascript
dd.scanCard({
  success: (res) => {
    const { NAME, IMAGE, PHONE, MPHONE, ADDRESS, COMPANY, POSITION } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{
  "NAME": "李乔",
  "IMAGE": "http://www.taobao.com/xxx.jpg",
  "PHONE": "01087654321",
  "MPHONE": "861333567890",
  "ADDRESS": "深圳市南山区软件产业基地",
  "COMPANY": "深圳市李乔科技有限公司",
  "POSITION": "CEO"
}
```