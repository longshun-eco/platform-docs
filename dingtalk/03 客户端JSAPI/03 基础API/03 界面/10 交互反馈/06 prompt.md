---
title: "prompt"
source: "https://open.dingtalk.com/document/development/jsapi-prompt"
category: "客户端JSAPI / 基础API / 界面 / 交互反馈"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-prompt_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-prompt_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

弹出输出入对话框

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11630) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11630) |

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
| message | String | 是 | 提示内容 | 消息内容 |
| title | String | 是 | 提示 | 消息标题 |
| placeholder | String | 是 | 占位字符示例 | 提示输入内容占位字符 |
| okButtonText | String | 是 | 确认 | 确认按钮文案 |
| cancelButtonText | String | 是 | 取消 | 取消按钮文案 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| buttonIndex | Number | 1 | 被点击按钮的索引值，Number类型，从0开始。 |
| value | String | 提示输入内容 | 输入的值 |

## **示例****代码**

### 默认出入参

```javascript
dd.prompt({
  title: '提示',
  message: '提示内容',
  placeholder: '提示输入内容占位字符',
  okButtonText: '确认',
  cancelButtonText: '取消',
  success: (res) => {
    const { value, buttonIndex } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "value": "提示输入内容", "buttonIndex": 1 }
```