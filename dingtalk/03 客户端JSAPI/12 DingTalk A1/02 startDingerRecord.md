---
title: "startDingerRecord"
source: "https://open.dingtalk.com/document/development/jsapi-start-dinger-record"
category: "客户端JSAPI / DingTalk A1"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-start-dinger-record_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-start-dinger-record_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-02-25

DingTalk A1 发起录音

DingTalk A1 发起录音

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 8.2.10 | 8.2.10 | 8.0.27 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11937) |
| 小程序 | 8.2.10 | 8.2.10 | 8.0.27 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11937) |

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
| templateId | String | 否 | xxx | 纪要模板 ID |
| businessOrder | String | 否 | xxx | 业务自定义 ID |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| fid | Number | 12345 | 录音记录ID |

## **示例****代码**

### 默认Demo标题

```
dd.startDingerRecord({
  templateId: 'xxx',
  businessOrder: 'xxx',
  success: (res) => {
    // res: 12345
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```

```