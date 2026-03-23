---
title: "chooseDingTalkDir"
source: "https://open.dingtalk.com/document/development/jsapi-choose-ding-talk-dir"
category: "客户端JSAPI / 协同 / 钉盘"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-choose-ding-talk-dir_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-choose-ding-talk-dir_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用chooseDingTalkDir，唤起钉盘选择器， 从用户当前的企业空间或个人空间选择一个目录， 用以保存文件等操作。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10319) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10319) |

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
| corpId | String | 否 | ding\*\* | 企业corpId。  H5应用中必填。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| data | Array<Object> |  | 文件信息。 |

## **示例****代码**

### 默认出入参

```javascript
dd.chooseDingTalkDir({
  corpId: 'ding',
  success: (res) => {
    const { data } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "data": [{ "path": "/path/to", "dirId": "dddd", "spaceId": "xxxx" }] }
```